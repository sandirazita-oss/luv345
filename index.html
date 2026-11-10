
// ===================================
// 1. DATA MENU MARTABAK
// ===================================

let products = JSON.parse(localStorage.getItem("martabakProducts")) || [
    {id: 1, name: "Martabak Cokelat", price: 20000, stock: 10, image: "martabak coklat.jpg"},
    {id: 2, name: "Martabak Keju", price: 23000, stock: 10, image: "martabak keju.jpg"},
    {id: 3, name: "Martabak Cokelat Keju", price: 27000, stock: 10, image: "martabak coklat keju.jpg"},
    {id: 4, name: "Martabak Kacang Cokelat", price: 25000, stock: 8, image: "coklat kacang.jpg"},
    {id: 5, name: "Martabak Telur Biasa", price: 22000, stock: 10,  image: "telur biasa.jpg"},
    {id: 6, name: "Martabak Telur Spesial", price: 30000, stock: 8, image: "telur spesial.jpg"}
];

let cart = [];

let transactions = JSON.parse(
    localStorage.getItem("martabakTransactions")
) || [];


// ===================================
// 2. PENYIMPANAN DATA
// ===================================

function saveData() {
    localStorage.setItem(
        "martabakProducts",
        JSON.stringify(products)
    );

    localStorage.setItem(
        "martabakTransactions",
        JSON.stringify(transactions)
    );
}


// ===================================
// 3. FORMAT RUPIAH
// ===================================

function rupiah(number) {
    return "Rp" + Number(number).toLocaleString("id-ID");
}


// ===================================
// 4. MENAMPILKAN MENU
// ===================================

function renderProducts() {

    const list = document.getElementById("productList");

    list.innerHTML = "";

    products.forEach(product => {

        let stockStatus = "";

        if (product.stock === 0) {
            stockStatus = `<span class="badge bg-danger">Habis</span>`;
        } else if (product.stock < 5) {
            stockStatus = `<span class="badge bg-warning text-dark">Stok Menipis</span>`;
        } else {
            stockStatus = `<span class="badge bg-success">Tersedia</span>`;
        }

        list.innerHTML += `
            <div class="col-md-6 col-lg-4">

                <div class="card product-card">

                    <div class="food-image">
                        ${product.emoji}
                    </div>

                    <div class="card-body">

                        <h5 class="fw-bold">
                            ${product.name}
                        </h5>

                        <p class="price">
                            ${rupiah(product.price)}
                        </p>

                        ${stockStatus}

                        <p class="text-secondary small mt-2">
                            Stok tersedia: ${product.stock}
                        </p>

                        <button
                            class="btn btn-brown w-100"
                            onclick="addToCart(${product.id})"
                            ${product.stock === 0 ? "disabled" : ""}>
                            ${product.stock === 0 ? "Stok Habis" : "Tambah Pesanan"}
                        </button>

                    </div>
                </div>

            </div>
        `;

    });

}


// ===================================
// 5. MENAMBAHKAN KE KERANJANG
// ===================================

function addToCart(id) {

    const product = products.find(p => p.id === id);

    if (!product || product.stock <= 0) {
        alert("Maaf, stok martabak habis!");
        return;
    }

    const item = cart.find(c => c.id === id);

    if (item) {

        if (item.qty >= product.stock) {
            alert("Jumlah pesanan melebihi stok!");
            return;
        }

        item.qty++;

    } else {

        cart.push({
            id: product.id,
            name: product.name,
            price: product.price,
            qty: 1
        });

    }

    renderCart();

}


// ===================================
// 6. MENAMPILKAN KERANJANG
// ===================================

function renderCart() {

    const list = document.getElementById("cartList");

    list.innerHTML = "";

    if (cart.length === 0) {

        list.innerHTML = `
            <p class="text-secondary">
                Belum ada pesanan.
            </p>
        `;

    }

    cart.forEach(item => {

        list.innerHTML += `

            <div class="d-flex justify-content-between
                align-items-center border-bottom py-3">

                <div>
                    <b>${item.name}</b>

                    <div class="text-secondary small">
                        ${rupiah(item.price)} x ${item.qty}
                    </div>
                </div>

                <div class="text-end">

                    <b>${rupiah(item.price * item.qty)}</b>

                    <div class="mt-2">

                        <button class="btn btn-sm btn-outline-secondary"
                            onclick="changeQty(${item.id}, -1)">
                            -
                        </button>

                        <button class="btn btn-sm btn-outline-secondary"
                            onclick="changeQty(${item.id}, 1)">
                            +
                        </button>

                        <button class="btn btn-sm btn-outline-danger"
                            onclick="removeItem(${item.id})">
                            Hapus
                        </button>

                    </div>

                </div>

            </div>

        `;

    });

    updatePayment();

}


// ===================================
// 7. MENGUBAH JUMLAH PESANAN
// ===================================

function changeQty(id, amount) {

    const item = cart.find(c => c.id === id);

    const product = products.find(p => p.id === id);

    if (!item || !product) return;

    const newQty = item.qty + amount;

    if (newQty <= 0) {
        removeItem(id);
        return;
    }

    if (newQty > product.stock) {
        alert("Stok tidak mencukupi!");
        return;
    }

    item.qty = newQty;

    renderCart();

}


// ===================================
// 8. MENGHAPUS PESANAN
// ===================================

function removeItem(id) {

    cart = cart.filter(item => item.id !== id);

    renderCart();

}


// ===================================
// 9. MENGHITUNG TOTAL
// ===================================

function getTotal() {

    return cart.reduce(
        (sum, item) => sum + item.price * item.qty,
        0
    );

}


// ===================================
// 10. PILIHAN PEMBAYARAN
// ===================================

document.querySelectorAll('input[name="payment"]')
.forEach(input => {

    input.addEventListener("change", updatePayment);

});

document.getElementById("uang")
.addEventListener("input", updatePayment);


// ===================================
// 11. VALIDASI PEMBAYARAN
// ===================================

function updatePayment() {

    const total = getTotal();

    const uang = Number(
        document.getElementById("uang").value
    );

    const metode = document.querySelector(
        'input[name="payment"]:checked'
    ).value;

    const cashBox = document.getElementById("cashBox");

    const paymentInfo = document.getElementById("paymentInfo");

    const orderBtn = document.getElementById("orderBtn");

    document.getElementById("total").textContent =
        rupiah(total);

    let valid = cart.length > 0;

    if (metode === "Tunai") {

        cashBox.style.display = "block";

        paymentInfo.style.display = "none";

        const change = uang - total;

        document.getElementById("change").textContent =
            rupiah(change > 0 ? change : 0);

        if (uang < total) {
            valid = false;
        }

    } else {

        cashBox.style.display = "none";

        paymentInfo.style.display = "block";

        paymentInfo.innerHTML = `
            <b>Pembayaran ${metode}</b><br>
            Metode ini masih dalam simulasi projek.
            Pembayaran belum terhubung ke bank atau
            penyedia QRIS sungguhan.
        `;

    }

    orderBtn.disabled = !valid;

}


// ===================================
// 12. MEMBUAT PESANAN
// ===================================

document.getElementById("orderBtn")
.addEventListener("click", function() {

    const nama = document.getElementById("nama").value.trim();

    const telepon = document.getElementById("telepon").value.trim();

    const metode = document.querySelector(
        'input[name="payment"]:checked'
    ).value;

    const total = getTotal();

    const uang = Number(document.getElementById("uang").value);

    if (!nama || !telepon) {
        alert("Silakan isi nama dan nomor WhatsApp!");
        return;
    }

    if (cart.length === 0) {
        alert("Keranjang masih kosong!");
        return;
    }

    // Memeriksa stok kembali
    for (const item of cart) {

        const product = products.find(p => p.id === item.id);

        if (!product || item.qty > product.stock) {
            alert("Stok produk tidak mencukupi!");
            return;
        }

    }

    if (metode === "Tunai" && uang < total) {
        alert("Uang pembayaran belum cukup!");
        return;
    }

    // Mengurangi stok
    cart.forEach(item => {

        const product = products.find(p => p.id === item.id);

        product.stock -= item.qty;

    });

    // Membuat data transaksi
    const trx = {

        id: "MRT-" + Date.now(),

        nama: nama,

        telepon: telepon,

        tanggal: new Date().toLocaleString("id-ID"),

        total: total,

        metode: metode,

        uang: metode === "Tunai" ? uang : 0,

        kembalian: metode === "Tunai" ? uang - total : 0,

        status: metode === "Tunai"
            ? "Pesanan dibuat - bayar di kasir"
            : "Menunggu pembayaran (simulasi)",

        items: cart.map(item => ({...item}))

    };

    transactions.push(trx);

    saveData();

    createReceipt(trx);

    // Mengosongkan keranjang
    cart = [];

    document.getElementById("uang").value = "";

    renderCart();

    renderProducts();

    alert("Pesanan berhasil dibuat!");

    document.getElementById("receiptSection").style.display = "block";

    document.getElementById("receiptSection")
        .scrollIntoView({behavior: "smooth"});

});


// ===================================
// 13. MEMBUAT NOTA PEMBELIAN
// ===================================

function createReceipt(trx) {

    let content = `

        <p><b>ID Pesanan:</b> ${trx.id}</p>

        <p><b>Nama:</b> ${trx.nama}</p>

        <p><b>WhatsApp:</b> ${trx.telepon}</p>

        <p><b>Tanggal:</b> ${trx.tanggal}</p>

        <hr>

    `;

    trx.items.forEach(item => {

        content += `

            <div class="d-flex justify-content-between mb-2">

                <span>
                    ${item.name} (${item.qty}x)
                </span>

                <b>
                    ${rupiah(item.price * item.qty)}
                </b>

            </div>

        `;

    });

    content += `

        <hr>

        <div class="d-flex justify-content-between">
            <b>Total Belanja</b>
            <b>${rupiah(trx.total)}</b>
        </div>

        <p class="mt-2">
            Metode Pembayaran: ${trx.metode}
        </p>

        <p>
            Status: ${trx.status}
        </p>

    `;

    if (trx.metode === "Tunai") {

        content += `

            <p>Uang Dibayar: ${rupiah(trx.uang)}</p>

            <p>Kembalian: ${rupiah(trx.kembalian)}</p>

        `;

    }

    document.getElementById("receiptContent").innerHTML =
        content;

}


// ===================================
// 14. MENJALANKAN APLIKASI
// ===================================

renderProducts();

renderCart();

updatePayment();
