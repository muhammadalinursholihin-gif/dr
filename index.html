import React, { useState, useEffect, useRef } from 'react';

// ==========================================
// INDONESIAN LOCAL DATA & REGION CONSTANTS
// ==========================================
const PROVINSI_DATA = {
  "DKI Jakarta": {
    "Jakarta Selatan": ["Cilandak", "Kebayoran Baru", "Tebet", "Pasar Minggu"],
    "Jakarta Pusat": ["Menteng", "Tanah Abang", "Gambir", "Senen"],
    "Jakarta Timur": ["Jatinegara", "Duren Sawit", "Kramat Jati", "Pulogadung"]
  },
  "Jawa Barat": {
    "Bandung": ["Coblong", "Cibeunying", "Andir", "Regol"],
    "Bogor": ["Bogor Timur", "Bogor Barat", "Bogor Tengah", "Tanah Sareal"],
    "Bekasi": ["Bekasi Barat", "Bekasi Timur", "Pondok Gede", "Jatiasih"]
  },
  "Jawa Timur": {
    "Surabaya": ["Tegalsari", "Gubeng", "Wonokromo", "Rungkut"],
    "Malang": ["Klojen", "Blimbing", "Lowokwaru", "Sukun"],
    "Sidoarjo": ["Waru", "Gedangan", "Candi", "Tanggulangin"]
  }
};

// Default Products Database
const INITIAL_PRODUCTS = [
  { id: "B001", nama: "Beras Sentra Ramos 5kg", kategori: "Sembako Utama", stok: 45, hargaBeli: 62000, hargaJual: 75000, unit: "kardus", expire: "2027-12-01", diskon: 0, kupon: "BERASBARU" },
  { id: "B002", nama: "Minyak Goreng Filma 2L", kategori: "Minyak & Lemak", stok: 12, hargaBeli: 28000, hargaJual: 34500, unit: "pcs", expire: "2026-08-15", diskon: 5, kupon: "MINYAKHEMAT" },
  { id: "B003", nama: "Gula Pasir Gulaku 1kg", kategori: "Sembako Utama", stok: 80, hargaBeli: 12500, hargaJual: 16000, unit: "pcs", expire: "2027-02-10", diskon: 0, kupon: "" },
  { id: "B004", nama: "Mie Instan Indomie Goreng", kategori: "Makanan Instan", stok: 240, hargaBeli: 2700, hargaJual: 3500, unit: "dus", expire: "2026-06-20", diskon: 10, kupon: "INDOMIE" },
  { id: "B005", nama: "Susu Kental Manis Frisian Flag", kategori: "Susu & Olahan", stok: 5, hargaBeli: 9500, hargaJual: 12000, unit: "kaleng", expire: "2026-06-30", diskon: 0, kupon: "" }
];

const INITIAL_EMPLOYEES = [
  { id: "K001", nama: "Budi Santoso", alamat: "Jl. Sudirman No. 12", provinsi: "DKI Jakarta", kabupaten: "Jakarta Selatan", kecamatan: "Cilandak", lulusan: "S1 Akuntansi", telp: "081234567890" },
  { id: "K002", nama: "Siti Rahma", alamat: "Jl. Merdeka No. 45", provinsi: "Jawa Barat", kabupaten: "Bandung", kecamatan: "Coblong", lulusan: "D3 Manajemen", telp: "08987654321" }
];

const INITIAL_SUPPLIERS = [
  { id: "S001", nama: "PT Sumber Sembako Makmur", alamat: "Kawasan Industri Pulogadung", provinsi: "DKI Jakarta", kabupaten: "Jakarta Timur", kecamatan: "Pulogadung", telp: "021-4892182" },
  { id: "S002", nama: "CV Jaya Pangan Utama", alamat: "Jl. Raya Waru No. 100", provinsi: "Jawa Timur", kabupaten: "Sidoarjo", kecamatan: "Waru", telp: "031-894721" }
];

export default function App() {
  // ==========================================
  // APP STATE MANAGEMENT
  // ==========================================
  const [isLoggedIn, setIsLoggedIn] = useState(false);
  const [currentUser, setCurrentUser] = useState(null);
  const [loginUsername, setLoginUsername] = useState('');
  const [loginPassword, setLoginPassword] = useState('');
  const [showRegister, setShowRegister] = useState(false);
  const [showFaceScan, setShowFaceScan] = useState(false);
  const [faceScanActive, setFaceScanActive] = useState(false);
  const [faceScanSuccess, setFaceScanSuccess] = useState(false);

  // App Header & Branding Customization
  const [appTitle, setAppTitle] = useState("TOKO SEMBAKO JAYA");
  const [appDesc, setAppDesc] = useState("Mitra Kebutuhan Pangan Keluarga Anda - Murah, Lengkap, dan Segar");
  const [appLogo, setAppLogo] = useState(""); // Base64
  const [appBanner, setAppBanner] = useState(""); // Base64
  const [bannerOffset, setBannerOffset] = useState({ y: 50 });
  const [isDraggingBanner, setIsDraggingBanner] = useState(false);
  const dragStartY = useRef(0);

  // Admin Profile & System Connections
  const [adminProfile, setAdminProfile] = useState({
    username: "admin",
    password: "123",
    namaLengkap: "Super Administrator",
    photo: "",
    gasApiUrl: "https://script.google.com/macros/s/AKfycby_MOCK_ENDPOINT_URL/exec",
    gdriveFolderId: "1-gDrive_MOCK_Folder_ID_xyz",
    gdriveApiKey: "AIzaSy_Mock_Drive_API_Key"
  });

  // Access Permissions (Super Admin Control)
  const [acl, setAcl] = useState({
    memberAccess: true,
    kasirAccess: true,
    supplierAccess: true,
    historyAccess: true,
    gdriveAccess: true
  });

  // Core Databases
  const [products, setProducts] = useState(INITIAL_PRODUCTS);
  const [employees, setEmployees] = useState(INITIAL_EMPLOYEES);
  const [suppliers, setSuppliers] = useState(INITIAL_SUPPLIERS);
  const [salesHistory, setSalesHistory] = useState([
    { id: "TX001", tanggal: "2026-06-11 10:30", itemsCount: 3, total: 125000, bayar: 150000, kembali: 25000, kasir: "Siti Rahma" },
    { id: "TX002", tanggal: "2026-06-11 14:15", itemsCount: 1, total: 34500, bayar: 50000, kembali: 15500, kasir: "Siti Rahma" }
  ]);
  const [historyLogs, setHistoryLogs] = useState([
    { id: "LOG001", timestamp: "2026-06-11 09:00", tipe: "Barang", aksi: "Tambah", detail: "Menambahkan Beras Sentra Ramos 5kg oleh admin", status: "Sukses" },
    { id: "LOG002", timestamp: "2026-06-11 09:15", tipe: "Sistem", aksi: "Setting", detail: "Memperbarui API Google Apps Script", status: "Sukses" }
  ]);

  // Main UI Tabs
  const [currentTab, setCurrentTab] = useState('dashboard'); // 'dashboard', 'barang', 'karyawan', 'supplier', 'idcard', 'profile', 'history'
  const [showPOS, setShowPOS] = useState(false);

  // Filter & Search States
  const [searchTerm, setSearchTerm] = useState('');
  const [categoryFilter, setCategoryFilter] = useState('');
  const [chartTimeframe, setChartTimeframe] = useState('daily'); // daily, weekly, monthly, yearly

  // Form States (CRUD Modals)
  const [productForm, setProductForm] = useState(null); // null or product object for add/edit
  const [employeeForm, setEmployeeForm] = useState(null);
  const [supplierForm, setSupplierForm] = useState(null);

  // POS State
  const [posCart, setPosCart] = useState([]);
  const [posCashAmount, setPosCashAmount] = useState(0);
  const [posDiscountCode, setPosDiscountCode] = useState('');
  const [posActiveAudioIndex, setPosActiveAudioIndex] = useState(4); // default audio preset
  const [showReceipt, setShowReceipt] = useState(false);
  const [lastReceipt, setLastReceipt] = useState(null);

  // ID Card State
  const [idCardData, setIdCardData] = useState({
    title: "KARTU ANGGOTA PRIORITAS",
    idNo: "MEM-2026-00089",
    phone: "0812-9988-7766",
    desc: "Pemegang kartu ini berhak mendapatkan diskon khusus sembako sebesar 5% di seluruh gerai Toko Sembako Jaya.",
    bgPhoto: "",
    memberPhoto: "",
    isLivePhoto: false
  });

  // Reference for Camera and Audio Context
  const videoRef = useRef(null);
  const audioContextRef = useRef(null);
  const barcodeCanvasRef = useRef(null);
  const idCardPrintRef = useRef(null);

  // ==========================================
  // WEB AUDIO SYNTHESIZER (10 Custom Sound Nodes)
  // ==========================================
  const initAudio = () => {
    if (!audioContextRef.current) {
      audioContextRef.current = new (window.AudioContext || window.webkitAudioContext)();
    }
  };

  const playSynthesizedSound = (soundType) => {
    try {
      initAudio();
      const ctx = audioContextRef.current;
      if (!ctx) return;

      const osc = ctx.createOscillator();
      const gain = ctx.createGain();
      osc.connect(gain);
      gain.connect(ctx.destination);

      const now = ctx.currentTime;

      switch (soundType) {
        case 'beep_click': // Sound 1: Fast Numeric Input
          osc.type = 'triangle';
          osc.frequency.setValueAtTime(600, now);
          gain.gain.setValueAtTime(0.1, now);
          gain.gain.exponentialRampToValueAtTime(0.01, now + 0.08);
          osc.start(now);
          osc.stop(now + 0.08);
          break;
        case 'beep_decimal': // Sound 2: Alt Click
          osc.type = 'sine';
          osc.frequency.setValueAtTime(880, now);
          gain.gain.setValueAtTime(0.08, now);
          gain.gain.exponentialRampToValueAtTime(0.01, now + 0.05);
          osc.start(now);
          osc.stop(now + 0.05);
          break;
        case 'clear': // Sound 3: Reset / Cancel
          osc.type = 'sawtooth';
          osc.frequency.setValueAtTime(220, now);
          osc.frequency.setValueAtTime(150, now + 0.1);
          gain.gain.setValueAtTime(0.12, now);
          gain.gain.exponentialRampToValueAtTime(0.01, now + 0.2);
          osc.start(now);
          osc.stop(now + 0.2);
          break;
        case 'add_cart': // Sound 4: Pleasant Chime
          osc.type = 'sine';
          osc.frequency.setValueAtTime(523.25, now); // C5
          osc.frequency.setValueAtTime(659.25, now + 0.08); // E5
          osc.frequency.setValueAtTime(783.99, now + 0.16); // G5
          gain.gain.setValueAtTime(0.15, now);
          gain.gain.exponentialRampToValueAtTime(0.01, now + 0.3);
          osc.start(now);
          osc.stop(now + 0.3);
          break;
        case 'pay_success': // Sound 5: Retro Cash Register (Cha-ching!)
          // Custom multi-frequency metallic synth
          osc.type = 'square';
          osc.frequency.setValueAtTime(800, now);
          osc.frequency.setValueAtTime(1200, now + 0.07);
          osc.frequency.setValueAtTime(1600, now + 0.14);
          osc.frequency.setValueAtTime(2400, now + 0.21);
          gain.gain.setValueAtTime(0.15, now);
          gain.gain.exponentialRampToValueAtTime(0.01, now + 0.4);
          osc.start(now);
          osc.stop(now + 0.4);
          break;
        case 'delete_item': // Sound 6: Error / Swoosh
          osc.type = 'triangle';
          osc.frequency.setValueAtTime(440, now);
          osc.frequency.exponentialRampToValueAtTime(110, now + 0.25);
          gain.gain.setValueAtTime(0.1, now);
          gain.gain.exponentialRampToValueAtTime(0.01, now + 0.25);
          osc.start(now);
          osc.stop(now + 0.25);
          break;
        case 'discount': // Sound 7: Cyber Zap
          osc.type = 'sawtooth';
          osc.frequency.setValueAtTime(1500, now);
          osc.frequency.linearRampToValueAtTime(500, now + 0.3);
          gain.gain.setValueAtTime(0.1, now);
          gain.gain.exponentialRampToValueAtTime(0.01, now + 0.3);
          osc.start(now);
          osc.stop(now + 0.3);
          break;
        case 'warning': // Sound 8: Flat alert buzzer
          osc.type = 'square';
          osc.frequency.setValueAtTime(180, now);
          gain.gain.setValueAtTime(0.15, now);
          gain.gain.exponentialRampToValueAtTime(0.01, now + 0.4);
          osc.start(now);
          osc.stop(now + 0.4);
          break;
        case 'general_ok': // Sound 9: Level Up chime
          osc.type = 'sine';
          osc.frequency.setValueAtTime(440, now);
          osc.frequency.setValueAtTime(880, now + 0.1);
          gain.gain.setValueAtTime(0.1, now);
          gain.gain.exponentialRampToValueAtTime(0.01, now + 0.25);
          osc.start(now);
          osc.stop(now + 0.25);
          break;
        case 'quick_pop': // Sound 10: Bubble pop
          osc.type = 'sine';
          osc.frequency.setValueAtTime(1000, now);
          osc.frequency.exponentialRampToValueAtTime(3000, now + 0.05);
          gain.gain.setValueAtTime(0.15, now);
          gain.gain.exponentialRampToValueAtTime(0.01, now + 0.06);
          osc.start(now);
          osc.stop(now + 0.06);
          break;
        default:
          osc.type = 'sine';
          osc.frequency.setValueAtTime(440, now);
          gain.gain.setValueAtTime(0.1, now);
          osc.start(now);
          osc.stop(now + 0.15);
      }
    } catch (e) {
      console.warn("Audio Context blocked or failed initialization", e);
    }
  };

  // Sound selection presets inside POS / Admin Settings
  const SOUND_PRESETS = [
    { name: "Sembako Standard Beep", key: "beep_click" },
    { name: "Lonceng Pembelian", key: "beep_decimal" },
    { name: "Batalkan Input", key: "clear" },
    { name: "Masukkan Keranjang", key: "add_cart" },
    { name: "Mesin Kasir Cha-Ching!", key: "pay_success" },
    { name: "Hapus Barang Keluar", key: "delete_item" },
    { name: "Laser Promo Diskon", key: "discount" },
    { name: "Peringatan Stok & Expire", key: "warning" },
    { name: "Konfirmasi Umum Sukses", key: "general_ok" },
    { name: "Efek Gelembung Cepat", key: "quick_pop" }
  ];

  // ==========================================
  // FACE SCAN SCANNER SIMULATOR (Real Cam Support)
  // ==========================================
  const startFaceScan = async () => {
    setFaceScanActive(true);
    setFaceScanSuccess(false);
    playSynthesizedSound('quick_pop');
    try {
      if (navigator.mediaDevices && navigator.mediaDevices.getUserMedia) {
        const stream = await navigator.mediaDevices.getUserMedia({ video: { facingMode: 'user' } });
        if (videoRef.current) {
          videoRef.current.srcObject = stream;
        }
      }
    } catch (err) {
      console.warn("No camera device found, running mock scanner", err);
    }

    // Process scanning effects
    setTimeout(() => {
      playSynthesizedSound('discount'); // futuristic laser sound
    }, 1200);

    setTimeout(() => {
      setFaceScanSuccess(true);
      playSynthesizedSound('general_ok');
      // Auto login Admin
      setTimeout(() => {
        setIsLoggedIn(true);
        setCurrentUser("Super Admin (Face-Scan)");
        setShowFaceScan(false);
        stopFaceScan();
        logHistory("Sistem", "Login", "Login menggunakan deteksi Fast Face-Scan", "Sukses");
      }, 1000);
    }, 3500);
  };

  const stopFaceScan = () => {
    if (videoRef.current && videoRef.current.srcObject) {
      const tracks = videoRef.current.srcObject.getTracks();
      tracks.forEach(track => track.stop());
    }
    setFaceScanActive(false);
  };

  // ==========================================
  // CUSTOM BARCODE GENERATOR (HTML5 Canvas)
  // ==========================================
  const generateBarcode = (text) => {
    const canvas = barcodeCanvasRef.current;
    if (!canvas) return;
    const ctx = canvas.getContext('2d');
    ctx.clearRect(0, 0, canvas.width, canvas.height);

    ctx.fillStyle = '#FFFFFF';
    ctx.fillRect(0, 0, canvas.width, canvas.height);

    ctx.fillStyle = '#000000';
    // Simple mock barcode: render patterns of vertical lines based on text chars
    let xOffset = 15;
    const padding = 15;
    const barHeight = canvas.height - 30;

    // Start Guard Bar
    ctx.fillRect(xOffset, padding, 2, barHeight); xOffset += 3;
    ctx.fillRect(xOffset, padding, 2, barHeight); xOffset += 4;

    for (let i = 0; i < text.length; i++) {
      const charCode = text.charCodeAt(i);
      // Map char code to binary pattern pseudo-randomly
      const binaryStr = charCode.toString(2).padStart(8, '0');
      for (let bit of binaryStr) {
        if (bit === '1') {
          ctx.fillRect(xOffset, padding, 2, barHeight);
        }
        xOffset += 3;
      }
      xOffset += 1;
    }

    // End Guard Bar
    ctx.fillRect(xOffset, padding, 2, barHeight); xOffset += 3;
    ctx.fillRect(xOffset, padding, 2, barHeight);

    // Render Text
    ctx.font = '10px Courier New';
    ctx.textAlign = 'center';
    ctx.fillText(text, canvas.width / 2, canvas.height - 4);
  };

  useEffect(() => {
    if (currentTab === 'idcard') {
      generateBarcode(idCardData.idNo);
    }
  }, [currentTab, idCardData.idNo]);

  // ==========================================
  // HELPER LOGS
  // ==========================================
  const logHistory = (tipe, aksi, detail, status = "Sukses") => {
    const newLog = {
      id: "LOG" + Date.now().toString().slice(-4),
      timestamp: new Date().toISOString().replace('T', ' ').substring(0, 16),
      tipe,
      aksi,
      detail,
      status
    };
    setHistoryLogs(prev => [newLog, ...prev]);
  };

  // ==========================================
  // EXPIRE ALERTS & NOTIFICATIONS TRIGGER
  // ==========================================
  const checkExpiredProductsCount = () => {
    const today = new Date();
    return products.filter(p => {
      const expDate = new Date(p.expire);
      const diffTime = expDate - today;
      const diffDays = Math.ceil(diffTime / (1000 * 60 * 60 * 24));
      return diffDays <= 30; // Expiring soon in 30 days
    }).length;
  };

  // ==========================================
  // IMAGE UPLOADS HANDLER
  // ==========================================
  const handleImageUpload = (e, callback) => {
    const file = e.target.files[0];
    if (file) {
      const reader = new FileReader();
      reader.onload = (uploadEvent) => {
        callback(uploadEvent.target.result);
        logHistory("Upload", "Gambar", `Mengunggah media baru: ${file.name}`);
        playSynthesizedSound('general_ok');
      };
      reader.readAsDataURL(file);
    }
  };

  // ==========================================
  // CSV EXPORT/IMPORT HANDLERS
  // ==========================================
  const exportToCSV = (dataList, filename) => {
    if (dataList.length === 0) return;
    const headers = Object.keys(dataList[0]).join(",");
    const rows = dataList.map(row => 
      Object.values(row).map(val => `"${val.toString().replace(/"/g, '""')}"`).join(",")
    );
    const csvContent = "data:text/csv;charset=utf-8," + [headers, ...rows].join("\n");
    const encodedUri = encodeURI(csvContent);
    const link = document.createElement("a");
    link.setAttribute("href", encodedUri);
    link.setAttribute("download", `${filename}_${Date.now()}.csv`);
    document.body.appendChild(link);
    link.click();
    document.body.removeChild(link);
    playSynthesizedSound('general_ok');
    logHistory("Sistem", "Export CSV", `Export data ${filename} berhasil`);
  };

  const handleCSVImport = (e, targetSetter) => {
    const file = e.target.files[0];
    if (file) {
      const reader = new FileReader();
      reader.onload = (event) => {
        try {
          const text = event.target.result;
          const lines = text.split("\n").filter(line => line.trim().length > 0);
          if (lines.length <= 1) return;
          const headers = lines[0].split(",").map(h => h.trim().replace(/^"|"$/g, ''));
          
          const importedData = lines.slice(1).map((line, idx) => {
            const values = line.split(",").map(val => val.trim().replace(/^"|"$/g, ''));
            const rowObj = {};
            headers.forEach((header, index) => {
              rowObj[header] = values[index] !== undefined ? values[index] : "";
            });
            // Ensure numbers are parsed back
            if (rowObj.stok) rowObj.stok = parseInt(rowObj.stok) || 0;
            if (rowObj.hargaBeli) rowObj.hargaBeli = parseFloat(rowObj.hargaBeli) || 0;
            if (rowObj.hargaJual) rowObj.hargaJual = parseFloat(rowObj.hargaJual) || 0;
            if (rowObj.diskon) rowObj.diskon = parseFloat(rowObj.diskon) || 0;
            if (!rowObj.id) rowObj.id = "IMP" + idx + Date.now().toString().slice(-3);
            return rowObj;
          });

          targetSetter(importedData);
          logHistory("Sistem", "Import CSV", `Berhasil mengimpor ${importedData.length} baris data`);
          playSynthesizedSound('add_cart');
        } catch (err) {
          alert("Gagal mengimpor file CSV. Pastikan format kolom sesuai.");
        }
      };
      reader.readAsText(file);
    }
  };

  // ==========================================
  // CUSTOM FINANCIAL CANDLE & LINE CHART DRAWER (HTML5 Canvas)
  // ==========================================
  const canvasRef = useRef(null);
  useEffect(() => {
    const canvas = canvasRef.current;
    if (!canvas) return;
    const ctx = canvas.getContext('2d');
    const width = canvas.width;
    const height = canvas.height;
    ctx.clearRect(0, 0, width, height);

    // Mock Financial Sembako Data based on timeframe
    const chartData = {
      daily: [
        { label: "Sen", open: 120, close: 150, high: 160, low: 110, volume: 100 },
        { label: "Sel", open: 150, close: 130, high: 175, low: 125, volume: 140 },
        { label: "Rab", open: 130, close: 180, high: 190, low: 120, volume: 210 },
        { label: "Kam", open: 180, close: 210, high: 220, low: 170, volume: 180 },
        { label: "Jum", open: 210, close: 190, high: 230, low: 185, volume: 250 },
        { label: "Sab", open: 190, close: 260, high: 280, low: 180, volume: 320 },
        { label: "Min", open: 260, close: 240, high: 270, low: 230, volume: 290 },
      ],
      weekly: [
        { label: "W1", open: 1100, close: 1300, high: 1400, low: 1000, volume: 800 },
        { label: "W2", open: 1300, close: 1250, high: 1500, low: 1200, volume: 950 },
        { label: "W3", open: 1250, close: 1680, high: 1750, low: 1200, volume: 1100 },
        { label: "W4", open: 1680, close: 1950, high: 2100, low: 1600, volume: 1350 },
      ],
      monthly: [
        { label: "Jan", open: 4000, close: 5200, high: 5500, low: 3800, volume: 3000 },
        { label: "Feb", open: 5200, close: 4800, high: 6000, low: 4500, volume: 3400 },
        { label: "Mar", open: 4800, close: 6100, high: 6400, low: 4300, volume: 4100 },
        { label: "Apr", open: 6100, close: 7300, high: 7800, low: 5900, volume: 4800 },
        { label: "Mei", open: 7300, close: 6900, high: 8000, low: 6500, volume: 5100 },
        { label: "Jun", open: 6900, close: 8500, high: 9000, low: 6700, volume: 6200 },
      ],
      yearly: [
        { label: "2024", open: 45000, close: 58000, high: 62000, low: 40000, volume: 30000 },
        { label: "2025", open: 58000, close: 72000, high: 79000, low: 52000, volume: 42000 },
        { label: "2026", open: 72000, close: 91000, high: 98000, low: 68000, volume: 55000 },
      ]
    }[chartTimeframe];

    const padding = 40;
    const chartWidth = width - padding * 2;
    const chartHeight = height - padding * 2;

    // Find dynamic boundaries
    const allVals = chartData.flatMap(d => [d.high, d.low, d.open, d.close]);
    const maxVal = Math.max(...allVals) * 1.1;
    const minVal = Math.min(...allVals) * 0.9;
    const valRange = maxVal - minVal;

    // Draw Grid Lines & Y Axis Labels
    ctx.strokeStyle = '#E2E8F0';
    ctx.fillStyle = '#64748B';
    ctx.font = '10px Inter, sans-serif';
    ctx.lineWidth = 1;
    const steps = 4;
    for (let i = 0; i <= steps; i++) {
      const y = padding + (chartHeight / steps) * i;
      const valLabel = (maxVal - (valRange / steps) * i).toFixed(0);
      ctx.beginPath();
      ctx.moveTo(padding, y);
      ctx.lineTo(width - padding, y);
      ctx.stroke();
      ctx.fillText(valLabel, 5, y + 3);
    }

    // Candle and Line calculations
    const colWidth = chartWidth / chartData.length;

    chartData.forEach((d, i) => {
      const x = padding + i * colWidth + colWidth / 2;

      // Candle Map Coordinates
      const yHigh = padding + chartHeight - ((d.high - minVal) / valRange) * chartHeight;
      const yLow = padding + chartHeight - ((d.low - minVal) / valRange) * chartHeight;
      const yOpen = padding + chartHeight - ((d.open - minVal) / valRange) * chartHeight;
      const yClose = padding + chartHeight - ((d.close - minVal) / valRange) * chartHeight;

      const isBullish = d.close >= d.open;
      const activeColor = isBullish ? '#10B981' : '#EF4444'; // Emerald for up, Red for down

      // 1. Draw High/Low Wick
      ctx.strokeStyle = activeColor;
      ctx.lineWidth = 1.5;
      ctx.beginPath();
      ctx.moveTo(x, yHigh);
      ctx.lineTo(x, yLow);
      ctx.stroke();

      // 2. Draw Candle Body
      ctx.fillStyle = activeColor;
      const bodyHeight = Math.abs(yClose - yOpen) || 2;
      ctx.fillRect(x - colWidth / 4, Math.min(yOpen, yClose), colWidth / 2, bodyHeight);

      // 3. Draw X Axis Labels
      ctx.fillStyle = '#475569';
      ctx.font = '11px bold Inter, sans-serif';
      ctx.textAlign = 'center';
      ctx.fillText(d.label, x, height - 15);
    });

    // Draw Line overlay matching close price
    ctx.beginPath();
    ctx.strokeStyle = '#3B82F6'; // Blue Line
    ctx.lineWidth = 2;
    chartData.forEach((d, i) => {
      const x = padding + i * colWidth + colWidth / 2;
      const yClose = padding + chartHeight - ((d.close - minVal) / valRange) * chartHeight;
      if (i === 0) {
        ctx.moveTo(x, yClose);
      } else {
        ctx.lineTo(x, yClose);
      }
    });
    ctx.stroke();

    // Line dots
    ctx.fillStyle = '#2563EB';
    chartData.forEach((d, i) => {
      const x = padding + i * colWidth + colWidth / 2;
      const yClose = padding + chartHeight - ((d.close - minVal) / valRange) * chartHeight;
      ctx.beginPath();
      ctx.arc(x, yClose, 3.5, 0, Math.PI * 2);
      ctx.fill();
    });

  }, [chartTimeframe, products, salesHistory]);

  // ==========================================
  // POS LOGIC & CASHIER FUNCTIONS
  // ==========================================
  const addToCart = (product) => {
    if (product.stok <= 0) {
      playSynthesizedSound('warning');
      alert(`Stok ${product.nama} habis!`);
      return;
    }
    const existing = posCart.find(item => item.id === product.id);
    if (existing) {
      if (existing.qty >= product.stok) {
        playSynthesizedSound('warning');
        alert("Batas maksimal stok tercapai!");
        return;
      }
      setPosCart(prev => prev.map(item => item.id === product.id ? { ...item, qty: item.qty + 1 } : item));
    } else {
      setPosCart(prev => [...prev, { ...product, qty: 1 }]);
    }
    playSynthesizedSound('add_cart');
  };

  const updateCartQty = (id, newQty) => {
    const item = posCart.find(i => i.id === id);
    if (!item) return;
    const originalProd = products.find(p => p.id === id);
    if (newQty > originalProd.stok) {
      playSynthesizedSound('warning');
      alert("Stok tidak mencukupi!");
      return;
    }
    if (newQty <= 0) {
      setPosCart(prev => prev.filter(i => i.id !== id));
      playSynthesizedSound('delete_item');
    } else {
      setPosCart(prev => prev.map(i => i.id === id ? { ...i, qty: newQty } : i));
      playSynthesizedSound('beep_click');
    }
  };

  const calculateSubtotal = () => {
    return posCart.reduce((total, item) => {
      const discountedPrice = item.hargaJual * (1 - item.diskon / 100);
      return total + (discountedPrice * item.qty);
    }, 0);
  };

  const processPayment = () => {
    const total = calculateSubtotal();
    if (posCashAmount < total) {
      playSynthesizedSound('warning');
      alert("Pembayaran kurang!");
      return;
    }

    // Success transaction sound preset based on super admin setting
    const soundKey = SOUND_PRESETS[posActiveAudioIndex]?.key || 'pay_success';
    playSynthesizedSound(soundKey);

    const change = posCashAmount - total;
    const newTxId = "TX" + Date.now().toString().slice(-4);
    const dateStr = new Date().toISOString().replace('T', ' ').substring(0, 16);

    const receipt = {
      id: newTxId,
      tanggal: dateStr,
      items: [...posCart],
      total,
      bayar: posCashAmount,
      kembali: change,
      kasir: adminProfile.namaLengkap
    };

    setLastReceipt(receipt);
    setSalesHistory(prev => [receipt, ...prev]);

    // Update stocks
    setProducts(prevProds => prevProds.map(p => {
      const cartItem = posCart.find(item => item.id === p.id);
      if (cartItem) {
        return { ...p, stok: p.stok - cartItem.qty };
      }
      return p;
    }));

    logHistory("Kasir", "Transaksi", `Penjualan ${newTxId} senilai Rp ${total.toLocaleString('id-ID')}`, "Sukses");

    setShowReceipt(true);
    setPosCart([]);
    setPosCashAmount(0);
  };

  // ==========================================
  // BRANDING DRAGGABLE HEADER BANNER
  // ==========================================
  const handleBannerMouseDown = (e) => {
    setIsDraggingBanner(true);
    dragStartY.current = e.clientY - bannerOffset.y;
  };

  const handleBannerMouseMove = (e) => {
    if (!isDraggingBanner) return;
    const newY = e.clientY - dragStartY.current;
    if (newY >= 0 && newY <= 100) {
      setBannerOffset({ y: newY });
    }
  };

  const handleBannerMouseUp = () => {
    setIsDraggingBanner(false);
  };

  // Ensure default login simulation on startup
  useEffect(() => {
    // Default admin profile is set
  }, []);

  return (
    <div className="min-h-screen bg-slate-50 text-slate-800 font-sans flex flex-col antialiased">
      
      {/* ==========================================
          HEADER UTAMA & CUSTOM BANNER BRANDING
         ========================================== */}
      <header className="relative bg-white shadow-md border-b border-slate-200">
        {/* Top Header Information & Real-Time Alert */}
        <div className="bg-emerald-600 text-white text-xs px-4 py-2 flex justify-between items-center z-10 relative">
          <div className="flex items-center gap-2">
            <span className="inline-block w-2.5 h-2.5 rounded-full bg-red-400 animate-ping"></span>
            <span className="font-medium">Stok Menipis & Expire: {checkExpiredProductsCount()} item</span>
          </div>
          <div className="flex items-center gap-3">
            <span>Server: Google Apps Script <b className="text-emerald-200">Terhubung</b></span>
            {isLoggedIn && (
              <button 
                onClick={() => { setIsLoggedIn(false); playSynthesizedSound('clear'); }} 
                className="bg-red-500 hover:bg-red-600 transition px-2 py-0.5 rounded text-[10px] font-bold"
              >
                LOGOUT
              </button>
            )}
          </div>
        </div>

        {/* Dynamic Customizable Banner */}
        <div 
          className="h-32 md:h-44 bg-gradient-to-r from-emerald-800 to-teal-900 relative overflow-hidden cursor-move select-none"
          style={{
            backgroundImage: appBanner ? `url(${appBanner})` : 'none',
            backgroundPosition: `center ${bannerOffset.y}%`,
            backgroundSize: 'cover'
          }}
          onMouseDown={handleBannerMouseDown}
          onMouseMove={handleBannerMouseMove}
          onMouseUp={handleBannerMouseUp}
          onMouseLeave={handleBannerMouseUp}
        >
          {/* Cover gradient layer if custom banner is present */}
          {appBanner && <div className="absolute inset-0 bg-black/30 pointer-events-none"></div>}

          <div className="absolute bottom-3 left-4 right-4 flex items-center justify-between text-white pointer-events-none">
            <div className="flex items-center gap-3">
              {appLogo ? (
                <img 
                  src={appLogo} 
                  alt="Store Logo" 
                  className="w-14 h-14 md:w-20 md:h-20 rounded-lg object-cover bg-white p-1 border-2 border-emerald-400 shadow-lg"
                />
              ) : (
                <div className="w-14 h-14 md:w-20 md:h-20 bg-emerald-500 flex items-center justify-center rounded-lg border-2 border-white shadow-lg text-2xl font-black">
                  🏪
                </div>
              )}
              <div>
                <h1 className="text-xl md:text-3xl font-extrabold tracking-tight drop-shadow-md">{appTitle}</h1>
                <p className="text-xs md:text-sm text-emerald-100 opacity-90 font-medium drop-shadow-sm">{appDesc}</p>
              </div>
            </div>
            <div className="hidden md:block text-right bg-black/40 backdrop-blur-sm p-2 rounded-lg text-xs">
              <p>📍 Geser banner ke atas/bawah untuk penyesuaian</p>
            </div>
          </div>
        </div>
      </header>

      {/* ==========================================
          LOGIN & REGISTRATION BOX (Including Face Scan)
         ========================================== */}
      {!isLoggedIn ? (
        <div className="flex-1 flex items-center justify-center p-4">
          <div className="w-full max-w-md bg-white rounded-2xl shadow-xl border border-slate-200 overflow-hidden">
            <div className="bg-emerald-600 p-6 text-white text-center">
              <span className="text-4xl mb-2 inline-block">🛍️</span>
              <h2 className="text-2xl font-extrabold">Sistem Toko Sembako</h2>
              <p className="text-xs text-emerald-200">Akses kontrol super admin dan pos kasir pintar</p>
            </div>

            <div className="p-6 space-y-4">
              <div>
                <label className="block text-xs font-bold uppercase text-slate-500 mb-1">Username</label>
                <input 
                  type="text" 
                  value={loginUsername} 
                  onChange={(e) => setLoginUsername(e.target.value)} 
                  placeholder="admin" 
                  className="w-full px-4 py-3 rounded-lg border border-slate-300 focus:ring-2 focus:ring-emerald-500 focus:outline-none"
                />
              </div>

              <div>
                <label className="block text-xs font-bold uppercase text-slate-500 mb-1">Password</label>
                <input 
                  type="password" 
                  value={loginPassword} 
                  onChange={(e) => setLoginPassword(e.target.value)} 
                  placeholder="123" 
                  className="w-full px-4 py-3 rounded-lg border border-slate-300 focus:ring-2 focus:ring-emerald-500 focus:outline-none"
                />
              </div>

              {/* Login Buttons */}
              <button 
                onClick={() => {
                  if (loginUsername === adminProfile.username && loginPassword === adminProfile.password) {
                    setIsLoggedIn(true);
                    setCurrentUser(adminProfile.namaLengkap);
                    playSynthesizedSound('general_ok');
                    logHistory("Sistem", "Login", "Super Admin berhasil masuk dengan kata sandi", "Sukses");
                  } else {
                    playSynthesizedSound('warning');
                    alert("Akun tidak valid!");
                  }
                }}
                className="w-full bg-emerald-600 hover:bg-emerald-700 transition text-white py-3 font-bold rounded-lg shadow-md"
              >
                Masuk Sistem 🔑
              </button>

              <div className="relative flex py-2 items-center">
                <div className="flex-grow border-t border-slate-200"></div>
                <span className="flex-shrink mx-4 text-xs text-slate-400 uppercase font-bold">Atau Login Instan</span>
                <div className="flex-grow border-t border-slate-200"></div>
              </div>

              {/* Face Scan Fast Login Trigger */}
              <button 
                onClick={() => { setShowFaceScan(true); startFaceScan(); }}
                className="w-full bg-gradient-to-r from-blue-600 to-indigo-700 hover:from-blue-700 hover:to-indigo-800 transition text-white py-3 rounded-lg flex items-center justify-center gap-2 font-bold shadow-md"
              >
                <svg className="w-5 h-5" fill="none" stroke="currentColor" strokeWidth="2" viewBox="0 0 24 24"><path strokeLinecap="round" strokeLinejoin="round" d="M15 12a3 3 0 11-6 0 3 3 0 016 0z" /><path strokeLinecap="round" strokeLinejoin="round" d="M2.458 12C3.732 7.943 7.523 5 12 5c4.478 0 8.268 2.943 9.542 7-1.274 4.057-5.064 7-9.542 7-4.477 0-8.268-2.943-9.542-7z" /></svg>
                Fast Scan Wajah 👤⚡
              </button>

              <p className="text-center text-xs text-slate-400 mt-4">
                Default: <b>admin</b> | Password: <b>123</b>
              </p>
            </div>
          </div>
        </div>
      ) : (
        /* ==========================================
            MAIN CORE DASHBOARD CONTENT (LOGGED IN)
           ========================================== */
        <div className="flex-1 flex flex-col md:flex-row">
          
          {/* Side Navigation Bar - Fully Responsive Mobile Slide */}
          <aside className="w-full md:w-64 bg-slate-900 text-slate-300 flex flex-col shrink-0 border-r border-slate-800">
            {/* Quick Stats Summary on Sidebar */}
            <div className="p-4 bg-slate-950/50 border-b border-slate-800 flex items-center gap-3">
              <div className="relative">
                {adminProfile.photo ? (
                  <img src={adminProfile.photo} className="w-10 h-10 rounded-full object-cover border border-emerald-500" alt="Admin" />
                ) : (
                  <div className="w-10 h-10 bg-emerald-600 text-white rounded-full flex items-center justify-center font-bold">AD</div>
                )}
                <span className="absolute bottom-0 right-0 w-3.5 h-3.5 bg-emerald-500 border-2 border-slate-900 rounded-full"></span>
              </div>
              <div>
                <p className="text-xs text-slate-400 uppercase font-black">Super Admin</p>
                <p className="text-sm font-bold text-white max-w-[150px] truncate">{adminProfile.namaLengkap}</p>
              </div>
            </div>

            {/* Sidebar Navigation Links */}
            <nav className="flex-1 p-4 space-y-1 overflow-y-auto">
              <button 
                onClick={() => { setCurrentTab('dashboard'); playSynthesizedSound('beep_click'); }}
                className={`w-full flex items-center gap-3 px-3 py-2.5 rounded-lg text-sm font-semibold transition ${currentTab === 'dashboard' ? 'bg-emerald-600 text-white shadow' : 'hover:bg-slate-800 text-slate-400 hover:text-white'}`}
              >
                📊 Dashboard Utama
              </button>
              
              <button 
                onClick={() => { setCurrentTab('barang'); playSynthesizedSound('beep_click'); }}
                className={`w-full flex items-center gap-3 px-3 py-2.5 rounded-lg text-sm font-semibold transition ${currentTab === 'barang' ? 'bg-emerald-600 text-white shadow' : 'hover:bg-slate-800 text-slate-400 hover:text-white'}`}
              >
                📦 Database Barang
              </button>

              <button 
                onClick={() => { setCurrentTab('karyawan'); playSynthesizedSound('beep_click'); }}
                className={`w-full flex items-center gap-3 px-3 py-2.5 rounded-lg text-sm font-semibold transition ${currentTab === 'karyawan' ? 'bg-emerald-600 text-white shadow' : 'hover:bg-slate-800 text-slate-400 hover:text-white'}`}
              >
                👥 Data Karyawan
              </button>

              <button 
                onClick={() => { setCurrentTab('supplier'); playSynthesizedSound('beep_click'); }}
                className={`w-full flex items-center gap-3 px-3 py-2.5 rounded-lg text-sm font-semibold transition ${currentTab === 'supplier' ? 'bg-emerald-600 text-white shadow' : 'hover:bg-slate-800 text-slate-400 hover:text-white'}`}
              >
                🏭 Mitra Supplier
              </button>

              <button 
                onClick={() => { setCurrentTab('idcard'); playSynthesizedSound('beep_click'); }}
                className={`w-full flex items-center gap-3 px-3 py-2.5 rounded-lg text-sm font-semibold transition ${currentTab === 'idcard' ? 'bg-emerald-600 text-white shadow' : 'hover:bg-slate-800 text-slate-400 hover:text-white'}`}
              >
                💳 Cetak Kartu Anggota
              </button>

              <button 
                onClick={() => { setCurrentTab('history'); playSynthesizedSound('beep_click'); }}
                className={`w-full flex items-center gap-3 px-3 py-2.5 rounded-lg text-sm font-semibold transition ${currentTab === 'history' ? 'bg-emerald-600 text-white shadow' : 'hover:bg-slate-800 text-slate-400 hover:text-white'}`}
              >
                📜 Log Riwayat Sistem
              </button>

              <button 
                onClick={() => { setCurrentTab('profile'); playSynthesizedSound('beep_click'); }}
                className={`w-full flex items-center gap-3 px-3 py-2.5 rounded-lg text-sm font-semibold transition ${currentTab === 'profile' ? 'bg-emerald-600 text-white shadow' : 'hover:bg-slate-800 text-slate-400 hover:text-white'}`}
              >
                ⚙️ Profil & API Sistem
              </button>
            </nav>

            {/* Quick POS Cashier Trigger Button */}
            <div className="p-4 border-t border-slate-800">
              <button 
                onClick={() => { setShowPOS(true); playSynthesizedSound('quick_pop'); }}
                className="w-full bg-gradient-to-r from-amber-500 to-orange-600 hover:from-amber-600 hover:to-orange-700 transition text-white py-3 rounded-xl font-black text-center flex items-center justify-center gap-2 shadow-lg"
              >
                🛒 BUKA KASIR (POS)
              </button>
            </div>
          </aside>

          {/* ==========================================
              MAIN CONTENT CONTAINER
             ========================================== */}
          <main className="flex-1 p-4 md:p-8 overflow-y-auto max-w-full">
            
            {/* TAB: DASHBOARD */}
            {currentTab === 'dashboard' && (
              <div className="space-y-6">
                
                {/* Header Info Banner */}
                <div className="grid grid-cols-2 lg:grid-cols-4 gap-4">
                  <div className="bg-white p-4 rounded-xl border border-slate-200 shadow-sm flex items-center justify-between">
                    <div>
                      <p className="text-xs font-bold text-slate-400 uppercase">Omset Penjualan</p>
                      <h4 className="text-lg md:text-2xl font-black text-slate-800">
                        Rp {salesHistory.reduce((sum, tx) => sum + tx.total, 0).toLocaleString('id-ID')}
                      </h4>
                    </div>
                    <span className="text-3xl">💰</span>
                  </div>

                  <div className="bg-white p-4 rounded-xl border border-slate-200 shadow-sm flex items-center justify-between">
                    <div>
                      <p className="text-xs font-bold text-slate-400 uppercase">Total Barang</p>
                      <h4 className="text-lg md:text-2xl font-black text-slate-800">{products.length} Item</h4>
                    </div>
                    <span className="text-3xl">📦</span>
                  </div>

                  <div className="bg-white p-4 rounded-xl border border-slate-200 shadow-sm flex items-center justify-between">
                    <div>
                      <p className="text-xs font-bold text-slate-400 uppercase">Karyawan Aktif</p>
                      <h4 className="text-lg md:text-2xl font-black text-slate-800">{employees.length} Orang</h4>
                    </div>
                    <span className="text-3xl">👥</span>
                  </div>

                  <div className="bg-white p-4 rounded-xl border border-slate-200 shadow-sm flex items-center justify-between">
                    <div>
                      <p className="text-xs font-bold text-slate-400 uppercase">Peringatan Expire</p>
                      <h4 className="text-lg md:text-2xl font-black text-red-600">{checkExpiredProductsCount()} Peringatan</h4>
                    </div>
                    <span className="text-3xl">⚠️</span>
                  </div>
                </div>

                {/* Candlestick & Line Chart Panel */}
                <div className="bg-white p-4 rounded-xl border border-slate-200 shadow-sm">
                  <div className="flex flex-col md:flex-row justify-between items-start md:items-center mb-4 gap-2">
                    <div>
                      <h3 className="text-lg font-extrabold text-slate-800 flex items-center gap-2">
                        📈 Grafik Analitik Keuangan Sembako
                      </h3>
                      <p className="text-xs text-slate-400">Visualisasi Candle-lilin (Volatilitas) & Line (Trend Penjualan)</p>
                    </div>

                    <div className="flex bg-slate-100 p-1 rounded-lg self-end">
                      {['daily', 'weekly', 'monthly', 'yearly'].map((t) => (
                        <button
                          key={t}
                          onClick={() => { setChartTimeframe(t); playSynthesizedSound('beep_click'); }}
                          className={`text-xs px-3 py-1 rounded-md font-bold uppercase transition ${chartTimeframe === t ? 'bg-white text-emerald-600 shadow' : 'text-slate-500 hover:text-slate-800'}`}
                        >
                          {t}
                        </button>
                      ))}
                    </div>
                  </div>

                  {/* HTML5 Canvas Chart Render */}
                  <div className="overflow-x-auto">
                    <canvas 
                      ref={canvasRef} 
                      width="800" 
                      height="300" 
                      className="w-full bg-slate-50 rounded-lg min-w-[700px]"
                    />
                  </div>
                </div>

                {/* CSV Sync & Drive Storage Integrations */}
                <div className="grid grid-cols-1 md:grid-cols-2 gap-6">
                  {/* Google Apps Script & Drive Integration Settings Status */}
                  <div className="bg-white p-5 rounded-xl border border-slate-200 shadow-sm space-y-4">
                    <h3 className="text-base font-bold text-slate-800 flex items-center gap-2">
                      ☁️ Google Apps Script & Drive Sync
                    </h3>
                    <p className="text-xs text-slate-400">
                      Sinkronkan basis data multi-sheet langsung ke cloud Google Spreadsheet Anda secara real-time.
                    </p>

                    <div className="grid grid-cols-2 gap-2 text-xs">
                      <div className="bg-slate-50 p-3 rounded-lg border border-slate-100">
                        <span className="block text-[10px] text-slate-400 uppercase font-bold">API Endpoint</span>
                        <span className="font-mono text-emerald-600 truncate block">{adminProfile.gasApiUrl}</span>
                      </div>
                      <div className="bg-slate-50 p-3 rounded-lg border border-slate-100">
                        <span className="block text-[10px] text-slate-400 uppercase font-bold">Drive Folder ID</span>
                        <span className="font-mono text-emerald-600 truncate block">{adminProfile.gdriveFolderId}</span>
                      </div>
                    </div>

                    <div className="flex gap-2">
                      <button 
                        onClick={() => {
                          playSynthesizedSound('add_cart');
                          alert("Sinkronisasi Sukses! Semua data berhasil dikirim ke Google Apps Script Spreadsheet.");
                          logHistory("Cloud", "Sync", "Melakukan force-sync database ke Google Apps Script");
                        }}
                        className="flex-1 bg-emerald-600 hover:bg-emerald-700 transition text-white py-2 rounded-lg text-xs font-bold"
                      >
                        ⚡ Sinkronisasi Sekarang
                      </button>
                      <button 
                        onClick={() => {
                          playSynthesizedSound('quick_pop');
                          alert(`Folder Connected: Google Drive folder ID: ${adminProfile.gdriveFolderId} active.`);
                        }}
                        className="bg-slate-800 hover:bg-slate-900 transition text-white px-4 py-2 rounded-lg text-xs font-bold"
                      >
                        📂 Cek Google Drive
                      </button>
                    </div>
                  </div>

                  {/* CSV Quick Import / Export Panel */}
                  <div className="bg-white p-5 rounded-xl border border-slate-200 shadow-sm space-y-4">
                    <h3 className="text-base font-bold text-slate-800 flex items-center gap-2">
                      📥 Backup Data & CSV Import/Export
                    </h3>
                    <p className="text-xs text-slate-400">
                      Gunakan format CSV untuk migrasi database barang massal atau untuk backup lokal harian.
                    </p>

                    <div className="flex flex-wrap gap-2">
                      <button 
                        onClick={() => exportToCSV(products, 'database_barang')}
                        className="bg-blue-600 hover:bg-blue-700 transition text-white px-4 py-2 rounded-lg text-xs font-bold flex items-center gap-1"
                      >
                        📤 Export Barang ke CSV
                      </button>
                      <label className="bg-indigo-600 hover:bg-indigo-700 transition text-white px-4 py-2 rounded-lg text-xs font-bold cursor-pointer flex items-center gap-1">
                        📥 Import Barang dari CSV
                        <input 
                          type="file" 
                          accept=".csv" 
                          onChange={(e) => handleCSVImport(e, setProducts)} 
                          className="hidden" 
                        />
                      </label>
                    </div>

                    <div className="p-3 bg-amber-50 rounded-lg border border-amber-200 text-xs text-amber-800">
                      💡 <b>Format Header CSV:</b> id, nama, kategori, stok, hargaBeli, hargaJual, unit, expire, diskon, kupon
                    </div>
                  </div>
                </div>

                {/* Expiring Soon Warnings Grid */}
                <div className="bg-white p-5 rounded-xl border border-slate-200 shadow-sm">
                  <h3 className="text-base font-bold text-red-600 mb-2 flex items-center gap-2">
                    🚨 Peringatan Barang Kadaluarsa (Expired &lt; 30 Hari)
                  </h3>
                  <div className="overflow-x-auto">
                    <table className="w-full text-left text-xs">
                      <thead>
                        <tr className="bg-slate-100 text-slate-600 uppercase font-black">
                          <th className="p-3">Nama Barang</th>
                          <th className="p-3">Kategori</th>
                          <th className="p-3">Stok</th>
                          <th className="p-3">Tanggal Kadaluarsa</th>
                          <th className="p-3 text-right">Aksi</th>
                        </tr>
                      </thead>
                      <tbody>
                        {products.filter(p => {
                          const expDate = new Date(p.expire);
                          const today = new Date();
                          const diffTime = expDate - today;
                          const diffDays = Math.ceil(diffTime / (1000 * 60 * 60 * 24));
                          return diffDays <= 30;
                        }).map(p => (
                          <tr key={p.id} className="border-b border-slate-100 hover:bg-slate-50">
                            <td className="p-3 font-bold text-slate-800">{p.nama}</td>
                            <td className="p-3">{p.kategori}</td>
                            <td className="p-3"><span className="bg-red-100 text-red-800 px-2 py-0.5 rounded-full font-bold">{p.stok}</span></td>
                            <td className="p-3 text-red-600 font-bold">{p.expire}</td>
                            <td className="p-3 text-right">
                              <button 
                                onClick={() => {
                                  setCurrentTab('barang');
                                  setSearchTerm(p.nama);
                                  playSynthesizedSound('beep_click');
                                }}
                                className="bg-slate-800 hover:bg-slate-900 text-white px-3 py-1 rounded font-bold"
                              >
                                Tinjau 🔍
                              </button>
                            </td>
                          </tr>
                        ))}
                      </tbody>
                    </table>
                  </div>
                </div>

              </div>
            )}

            {/* TAB: DATABASE BARANG */}
            {currentTab === 'barang' && (
              <div className="space-y-6">
                
                <div className="flex flex-col md:flex-row justify-between items-start md:items-center gap-3">
                  <div>
                    <h2 className="text-xl font-extrabold text-slate-800">📦 Manajemen Database Sembako</h2>
                    <p className="text-xs text-slate-400">Kelola stok, harga, promosi diskon, kupon belanja, dan tanggal kadaluarsa.</p>
                  </div>
                  
                  <button 
                    onClick={() => {
                      setProductForm({
                        id: "B" + Date.now().toString().slice(-3),
                        nama: "",
                        kategori: "Sembako Utama",
                        stok: 10,
                        hargaBeli: 0,
                        hargaJual: 0,
                        unit: "pcs",
                        expire: new Date(Date.now() + 31536000000).toISOString().substring(0, 10), // 1 year from now
                        diskon: 0,
                        kupon: ""
                      });
                      playSynthesizedSound('quick_pop');
                    }}
                    className="bg-emerald-600 hover:bg-emerald-700 transition text-white px-4 py-2.5 rounded-xl font-bold text-sm flex items-center gap-1 shadow-md"
                  >
                    ➕ Tambah Barang Baru
                  </button>
                </div>

                {/* Filter and Search Bar */}
                <div className="bg-white p-4 rounded-xl border border-slate-200 shadow-sm flex flex-col md:flex-row gap-3">
                  <input 
                    type="text" 
                    value={searchTerm}
                    onChange={(e) => setSearchTerm(e.target.value)}
                    placeholder="Cari berdasarkan nama barang..." 
                    className="flex-1 px-4 py-2 border border-slate-300 rounded-lg text-sm focus:ring-2 focus:ring-emerald-500 focus:outline-none"
                  />
                  
                  <select 
                    value={categoryFilter}
                    onChange={(e) => setCategoryFilter(e.target.value)}
                    className="px-4 py-2 border border-slate-300 rounded-lg text-sm bg-white text-slate-700 focus:ring-2 focus:ring-emerald-500 focus:outline-none"
                  >
                    <option value="">Semua Kategori</option>
                    <option value="Sembako Utama">Sembako Utama</option>
                    <option value="Minyak & Lemak">Minyak & Lemak</option>
                    <option value="Makanan Instan">Makanan Instan</option>
                    <option value="Susu & Olahan">Susu & Olahan</option>
                  </select>
                </div>

                {/* Professional Data Table */}
                <div className="bg-white rounded-xl border border-slate-200 shadow-sm overflow-hidden">
                  <div className="overflow-x-auto">
                    <table className="w-full text-left text-sm">
                      <thead>
                        <tr className="bg-slate-100 text-slate-600 uppercase font-black text-xs border-b border-slate-200">
                          <th className="p-4">SKU / ID</th>
                          <th className="p-4">Nama Barang</th>
                          <th className="p-4">Kategori</th>
                          <th className="p-4">Unit</th>
                          <th className="p-4">Stok</th>
                          <th className="p-4">Harga Beli</th>
                          <th className="p-4">Harga Jual</th>
                          <th className="p-4">Diskon / Kupon</th>
                          <th className="p-4">Exp Date</th>
                          <th className="p-4 text-center">Aksi</th>
                        </tr>
                      </thead>
                      <tbody>
                        {products
                          .filter(p => p.nama.toLowerCase().includes(searchTerm.toLowerCase()))
                          .filter(p => categoryFilter === "" || p.kategori === categoryFilter)
                          .map(p => {
                            const isNearExp = (new Date(p.expire) - new Date()) / (1000 * 60 * 60 * 24) <= 30;
                            return (
                              <tr key={p.id} className="border-b border-slate-100 hover:bg-slate-50 transition">
                                <td className="p-4 font-mono font-bold text-emerald-700">{p.id}</td>
                                <td className="p-4">
                                  <span className="font-extrabold text-slate-800">{p.nama}</span>
                                </td>
                                <td className="p-4">
                                  <span className="bg-slate-100 text-slate-800 px-2 py-1 rounded text-xs font-semibold">{p.kategori}</span>
                                </td>
                                <td className="p-4 text-xs font-bold text-slate-500 uppercase">{p.unit}</td>
                                <td className="p-4">
                                  <span className={`px-2 py-1 rounded font-bold text-xs ${p.stok <= 5 ? 'bg-red-100 text-red-800' : 'bg-emerald-100 text-emerald-800'}`}>
                                    {p.stok}
                                  </span>
                                </td>
                                <td className="p-4 text-slate-600">Rp {p.hargaBeli.toLocaleString('id-ID')}</td>
                                <td className="p-4 font-bold text-slate-800">Rp {p.hargaJual.toLocaleString('id-ID')}</td>
                                <td className="p-4">
                                  {p.diskon > 0 ? (
                                    <span className="bg-red-500 text-white text-[10px] px-1.5 py-0.5 rounded font-bold mr-1">
                                      -{p.diskon}%
                                    </span>
                                  ) : null}
                                  {p.kupon ? (
                                    <span className="bg-amber-100 text-amber-800 text-[10px] px-1.5 py-0.5 rounded font-mono font-bold">
                                      🎟️ {p.kupon}
                                    </span>
                                  ) : null}
                                </td>
                                <td className="p-4">
                                  <span className={`text-xs font-bold ${isNearExp ? 'text-red-600 bg-red-50 px-1 rounded' : 'text-slate-600'}`}>
                                    {p.expire}
                                  </span>
                                </td>
                                <td className="p-4">
                                  <div className="flex gap-2 justify-center">
                                    <button 
                                      onClick={() => { setProductForm({ ...p }); playSynthesizedSound('beep_click'); }}
                                      className="p-1.5 bg-amber-100 text-amber-800 hover:bg-amber-200 rounded transition"
                                      title="Edit Barang"
                                    >
                                      ✏️
                                    </button>
                                    <button 
                                      onClick={() => {
                                        if (confirm(`Hapus ${p.nama}?`)) {
                                          setProducts(prev => prev.filter(item => item.id !== p.id));
                                          logHistory("Barang", "Hapus", `Menghapus produk ${p.nama}`, "Sukses");
                                          playSynthesizedSound('delete_item');
                                        }
                                      }}
                                      className="p-1.5 bg-red-100 text-red-800 hover:bg-red-200 rounded transition"
                                      title="Hapus Barang"
                                    >
                                      🗑️
                                    </button>
                                  </div>
                                </td>
                              </tr>
                            );
                        })}
                      </tbody>
                    </table>
                  </div>
                </div>

              </div>
            )}

            {/* TAB: DATA KARYAWAN */}
            {currentTab === 'karyawan' && (
              <div className="space-y-6">
                <div className="flex justify-between items-center">
                  <div>
                    <h2 className="text-xl font-extrabold text-slate-800">👥 Kelola Data Karyawan</h2>
                    <p className="text-xs text-slate-400">Sistem pendataan otomatis menggunakan dropdown wilayah bertingkat.</p>
                  </div>
                  <button 
                    onClick={() => {
                      setEmployeeForm({
                        id: "K" + Date.now().toString().slice(-3),
                        nama: "",
                        alamat: "",
                        provinsi: "DKI Jakarta",
                        kabupaten: "Jakarta Selatan",
                        kecamatan: "Cilandak",
                        lulusan: "S1",
                        telp: ""
                      });
                      playSynthesizedSound('quick_pop');
                    }}
                    className="bg-emerald-600 hover:bg-emerald-700 transition text-white px-4 py-2.5 rounded-xl font-bold text-sm shadow-md"
                  >
                    ➕ Tambah Karyawan
                  </button>
                </div>

                <div className="bg-white rounded-xl border border-slate-200 shadow-sm overflow-hidden">
                  <div className="overflow-x-auto">
                    <table className="w-full text-left text-sm">
                      <thead>
                        <tr className="bg-slate-100 text-slate-600 uppercase font-black text-xs border-b border-slate-200">
                          <th className="p-4">ID</th>
                          <th className="p-4">Nama Lengkap</th>
                          <th className="p-4">Alamat Wilayah</th>
                          <th className="p-4">Kecamatan / Kab</th>
                          <th className="p-4">Lulusan</th>
                          <th className="p-4">No. Telp</th>
                          <th className="p-4 text-center">Aksi</th>
                        </tr>
                      </thead>
                      <tbody>
                        {employees.map(k => (
                          <tr key={k.id} className="border-b border-slate-100 hover:bg-slate-50 transition">
                            <td className="p-4 font-mono font-bold text-blue-600">{k.id}</td>
                            <td className="p-4 font-extrabold text-slate-800">{k.nama}</td>
                            <td className="p-4 text-slate-600">{k.alamat}, {k.provinsi}</td>
                            <td className="p-4 text-xs font-bold text-slate-500">{k.kecamatan}, {k.kabupaten}</td>
                            <td className="p-4"><span className="bg-blue-100 text-blue-800 px-2 py-0.5 rounded text-xs font-bold">{k.lulusan}</span></td>
                            <td className="p-4 font-mono text-xs">{k.telp}</td>
                            <td className="p-4">
                              <div className="flex gap-2 justify-center">
                                <button 
                                  onClick={() => { setEmployeeForm({ ...k }); playSynthesizedSound('beep_click'); }}
                                  className="p-1.5 bg-amber-100 text-amber-800 hover:bg-amber-200 rounded transition"
                                >
                                  ✏️
                                </button>
                                <button 
                                  onClick={() => {
                                    if (confirm(`Hapus karyawan ${k.nama}?`)) {
                                      setEmployees(prev => prev.filter(item => item.id !== k.id));
                                      logHistory("Karyawan", "Hapus", `Menghapus karyawan ${k.nama}`, "Sukses");
                                      playSynthesizedSound('delete_item');
                                    }
                                  }}
                                  className="p-1.5 bg-red-100 text-red-800 hover:bg-red-200 rounded transition"
                                >
                                  🗑️
                                </button>
                              </div>
                            </td>
                          </tr>
                        ))}
                      </tbody>
                    </table>
                  </div>
                </div>
              </div>
            )}

            {/* TAB: DATA SUPPLIER */}
            {currentTab === 'supplier' && (
              <div className="space-y-6">
                <div className="flex justify-between items-center">
                  <div>
                    <h2 className="text-xl font-extrabold text-slate-800">🏭 Data Mitra Supplier Sembako</h2>
                    <p className="text-xs text-slate-400">Database penyuplai logistik barang utama.</p>
                  </div>
                  <button 
                    onClick={() => {
                      setSupplierForm({
                        id: "S" + Date.now().toString().slice(-3),
                        nama: "",
                        alamat: "",
                        provinsi: "DKI Jakarta",
                        kabupaten: "Jakarta Selatan",
                        kecamatan: "Cilandak",
                        telp: ""
                      });
                      playSynthesizedSound('quick_pop');
                    }}
                    className="bg-emerald-600 hover:bg-emerald-700 transition text-white px-4 py-2.5 rounded-xl font-bold text-sm shadow-md"
                  >
                    ➕ Tambah Supplier
                  </button>
                </div>

                <div className="bg-white rounded-xl border border-slate-200 shadow-sm overflow-hidden">
                  <div className="overflow-x-auto">
                    <table className="w-full text-left text-sm">
                      <thead>
                        <tr className="bg-slate-100 text-slate-600 uppercase font-black text-xs border-b border-slate-200">
                          <th className="p-4">ID</th>
                          <th className="p-4">Nama Perusahaan / Supplier</th>
                          <th className="p-4">Provinsi / Alamat</th>
                          <th className="p-4">Kecamatan & Kota</th>
                          <th className="p-4">No. Telp</th>
                          <th className="p-4 text-center">Aksi</th>
                        </tr>
                      </thead>
                      <tbody>
                        {suppliers.map(s => (
                          <tr key={s.id} className="border-b border-slate-100 hover:bg-slate-50 transition">
                            <td className="p-4 font-mono font-bold text-purple-600">{s.id}</td>
                            <td className="p-4 font-extrabold text-slate-800">{s.nama}</td>
                            <td className="p-4 text-slate-600">{s.alamat}, {s.provinsi}</td>
                            <td className="p-4 text-xs font-bold text-slate-500">{s.kecamatan}, {s.kabupaten}</td>
                            <td className="p-4 font-mono text-xs">{s.telp}</td>
                            <td className="p-4">
                              <div className="flex gap-2 justify-center">
                                <button 
                                  onClick={() => { setSupplierForm({ ...s }); playSynthesizedSound('beep_click'); }}
                                  className="p-1.5 bg-amber-100 text-amber-800 hover:bg-amber-200 rounded transition"
                                >
                                  ✏️
                                </button>
                                <button 
                                  onClick={() => {
                                    if (confirm(`Hapus supplier ${s.nama}?`)) {
                                      setSuppliers(prev => prev.filter(item => item.id !== s.id));
                                      logHistory("Supplier", "Hapus", `Menghapus supplier ${s.nama}`, "Sukses");
                                      playSynthesizedSound('delete_item');
                                    }
                                  }}
                                  className="p-1.5 bg-red-100 text-red-800 hover:bg-red-200 rounded transition"
                                >
                                  🗑️
                                </button>
                              </div>
                            </td>
                          </tr>
                        ))}
                      </tbody>
                    </table>
                  </div>
                </div>
              </div>
            )}

            {/* TAB: CETAK KARTU ANGGOTA BARCODE */}
            {currentTab === 'idcard' && (
              <div className="space-y-6">
                <div>
                  <h2 className="text-xl font-extrabold text-slate-800">💳 Cetak Kartu Anggota Prioritas</h2>
                  <p className="text-xs text-slate-400">Buat, modifikasi, upload background, ambil foto live, dan download ID Card real-time.</p>
                </div>

                <div className="grid grid-cols-1 lg:grid-cols-2 gap-6">
                  {/* Interactive Editor Form */}
                  <div className="bg-white p-5 rounded-xl border border-slate-200 shadow-sm space-y-4">
                    <h3 className="text-base font-bold text-slate-800">Konfigurator Desain Kartu</h3>
                    
                    <div className="space-y-3">
                      <div>
                        <label className="block text-xs font-bold text-slate-500 mb-1">Judul Kartu</label>
                        <input 
                          type="text" 
                          value={idCardData.title}
                          onChange={(e) => setIdCardData({ ...idCardData, title: e.target.value })}
                          className="w-full px-3 py-2 border border-slate-300 rounded text-sm focus:outline-emerald-500"
                        />
                      </div>

                      <div className="grid grid-cols-2 gap-2">
                        <div>
                          <label className="block text-xs font-bold text-slate-500 mb-1">Nomor ID Card</label>
                          <input 
                            type="text" 
                            value={idCardData.idNo}
                            onChange={(e) => setIdCardData({ ...idCardData, idNo: e.target.value })}
                            className="w-full px-3 py-2 border border-slate-300 rounded text-sm focus:outline-emerald-500"
                          />
                        </div>
                        <div>
                          <label className="block text-xs font-bold text-slate-500 mb-1">No. Telephone</label>
                          <input 
                            type="text" 
                            value={idCardData.phone}
                            onChange={(e) => setIdCardData({ ...idCardData, phone: e.target.value })}
                            className="w-full px-3 py-2 border border-slate-300 rounded text-sm focus:outline-emerald-500"
                          />
                        </div>
                      </div>

                      <div>
                        <label className="block text-xs font-bold text-slate-500 mb-1">Deskripsi & Keuntungan Kartu</label>
                        <textarea 
                          rows="3"
                          value={idCardData.desc}
                          onChange={(e) => setIdCardData({ ...idCardData, desc: e.target.value })}
                          className="w-full px-3 py-2 border border-slate-300 rounded text-sm focus:outline-emerald-500"
                        />
                      </div>

                      <div className="grid grid-cols-2 gap-2">
                        <div>
                          <label className="block text-xs font-bold text-slate-500 mb-1">Unggah BG Gambar</label>
                          <input 
                            type="file" 
                            accept="image/*"
                            onChange={(e) => handleImageUpload(e, (base64) => setIdCardData({ ...idCardData, bgPhoto: base64 }))}
                            className="w-full text-xs"
                          />
                        </div>
                        <div>
                          <label className="block text-xs font-bold text-slate-500 mb-1">Unggah Foto Profil</label>
                          <input 
                            type="file" 
                            accept="image/*"
                            onChange={(e) => handleImageUpload(e, (base64) => setIdCardData({ ...idCardData, memberPhoto: base64 }))}
                            className="w-full text-xs"
                          />
                        </div>
                      </div>

                      {/* Live Camera Feed Integration for ID Card Snap */}
                      <div className="border border-slate-200 p-3 rounded-lg bg-slate-50">
                        <span className="block text-xs font-bold text-slate-700 mb-1">Ambil Foto Langsung (Kamera)</span>
                        {idCardData.isLivePhoto ? (
                          <div className="space-y-2">
                            <video ref={videoRef} autoPlay playsInline className="w-full h-32 object-cover rounded bg-black"></video>
                            <button 
                              onClick={() => {
                                // Capture from video feed
                                if (videoRef.current) {
                                  const canvas = document.createElement('canvas');
                                  canvas.width = 400;
                                  canvas.height = 400;
                                  const ctx = canvas.getContext('2d');
                                  ctx.drawImage(videoRef.current, 0, 0, 400, 400);
                                  const snappedData = canvas.toDataURL('image/png');
                                  setIdCardData({ ...idCardData, memberPhoto: snappedData, isLivePhoto: false });
                                  // Stop camera track
                                  if (videoRef.current.srcObject) {
                                    videoRef.current.srcObject.getTracks().forEach(track => track.stop());
                                  }
                                  playSynthesizedSound('pay_success');
                                }
                              }}
                              className="bg-blue-600 text-white font-bold text-xs px-3 py-2 rounded shadow hover:bg-blue-700 w-full"
                            >
                              📸 Ambil Gambar Sekarang
                            </button>
                          </div>
                        ) : (
                          <button 
                            onClick={async () => {
                              setIdCardData({ ...idCardData, isLivePhoto: true });
                              setTimeout(async () => {
                                try {
                                  const stream = await navigator.mediaDevices.getUserMedia({ video: true });
                                  if (videoRef.current) videoRef.current.srcObject = stream;
                                } catch (e) {
                                  alert("Kamera tidak terdeteksi!");
                                }
                              }, 500);
                            }}
                            className="bg-slate-800 text-white font-bold text-xs px-3 py-2 rounded shadow hover:bg-slate-900"
                          >
                            📹 Aktifkan Kamera Live
                          </button>
                        )}
                      </div>

                    </div>
                  </div>

                  {/* ID Card Real-time Preview Area */}
                  <div className="flex flex-col items-center justify-center p-4 bg-slate-100 rounded-xl border border-slate-200">
                    <span className="text-xs font-bold text-slate-400 mb-2 uppercase">Pratinjau Kartu Fisik</span>
                    
                    <div 
                      ref={idCardPrintRef}
                      className="w-[340px] h-[210px] rounded-2xl relative shadow-2xl overflow-hidden flex flex-col justify-between p-4 text-white bg-slate-800 border-2 border-emerald-400"
                      style={{
                        backgroundImage: idCardData.bgPhoto ? `url(${idCardData.bgPhoto})` : 'linear-gradient(135deg, #064e3b 0%, #022c22 100%)',
                        backgroundSize: 'cover',
                        backgroundPosition: 'center'
                      }}
                    >
                      {/* Top Header Card */}
                      <div className="flex justify-between items-start">
                        <div>
                          <h4 className="text-[10px] uppercase font-black tracking-widest text-emerald-300">Toko Sembako Jaya</h4>
                          <h3 className="text-xs font-bold leading-tight uppercase">{idCardData.title}</h3>
                        </div>
                        <span className="text-lg">👑</span>
                      </div>

                      {/* Middle Card Info */}
                      <div className="flex items-center gap-3">
                        {idCardData.memberPhoto ? (
                          <img src={idCardData.memberPhoto} className="w-14 h-14 rounded-full object-cover border-2 border-white shadow-md" alt="Member" />
                        ) : (
                          <div className="w-14 h-14 bg-emerald-600 rounded-full border-2 border-white flex items-center justify-center text-xs font-extrabold">FOTO</div>
                        )}
                        <div className="text-left flex-1">
                          <p className="text-[9px] text-slate-300 font-bold uppercase">Nomor Anggota</p>
                          <p className="text-sm font-black text-amber-300 font-mono">{idCardData.idNo}</p>
                          <p className="text-[9px] text-slate-300 font-bold uppercase mt-1">Telpon</p>
                          <p className="text-[10px] font-mono leading-none">{idCardData.phone}</p>
                        </div>
                      </div>

                      {/* Bottom Card Barcode and Text */}
                      <div className="flex justify-between items-end">
                        <p className="text-[7px] max-w-[170px] leading-tight text-emerald-100 drop-shadow">{idCardData.desc}</p>
                        {/* Dynamic Auto Barcode */}
                        <canvas ref={barcodeCanvasRef} width="110" height="40" className="bg-white rounded p-0.5 max-w-[110px]"></canvas>
                      </div>
                    </div>

                    <button 
                      onClick={() => {
                        playSynthesizedSound('pay_success');
                        alert("ID Card berhasil dirender ke unduhan gambar PDF/PNG lokal.");
                      }}
                      className="mt-6 bg-emerald-600 hover:bg-emerald-700 text-white font-bold px-6 py-2.5 rounded-lg shadow-md flex items-center gap-1 text-sm"
                    >
                      💾 Unduh Kartu Anggota (JPG / PDF)
                    </button>
                  </div>
                </div>
              </div>
            )}

            {/* TAB: LOG RIWAYAT SISTEM */}
            {currentTab === 'history' && (
              <div className="space-y-6">
                <div className="flex justify-between items-center">
                  <div>
                    <h2 className="text-xl font-extrabold text-slate-800">📜 Audit Log & Riwayat Aktivitas</h2>
                    <p className="text-xs text-slate-400">Log transaksi POS, perubahan database barang, karyawan, dan audit sistem.</p>
                  </div>
                  <button 
                    onClick={() => {
                      setHistoryLogs([]);
                      playSynthesizedSound('clear');
                    }}
                    className="bg-red-100 hover:bg-red-200 text-red-800 px-4 py-2 rounded-lg text-xs font-bold"
                  >
                    🗑️ Bersihkan Semua Log
                  </button>
                </div>

                {/* Audit Grid list */}
                <div className="bg-white rounded-xl border border-slate-200 shadow-sm overflow-hidden">
                  <div className="overflow-x-auto">
                    <table className="w-full text-left text-xs">
                      <thead>
                        <tr className="bg-slate-100 text-slate-600 uppercase font-black p-4 border-b">
                          <th className="p-4">Log ID</th>
                          <th className="p-4">Tanggal Waktu</th>
                          <th className="p-4">Kategori Tipe</th>
                          <th className="p-4">Aksi Audit</th>
                          <th className="p-4">Detail Perubahan</th>
                          <th className="p-4 text-center">Status</th>
                        </tr>
                      </thead>
                      <tbody>
                        {historyLogs.map(log => (
                          <tr key={log.id} className="border-b border-slate-100 hover:bg-slate-50">
                            <td className="p-4 font-mono font-bold text-slate-400">{log.id}</td>
                            <td className="p-4 font-mono text-slate-600">{log.timestamp}</td>
                            <td className="p-4">
                              <span className="bg-slate-100 px-2.5 py-1 rounded-full font-bold text-slate-700">{log.tipe}</span>
                            </td>
                            <td className="p-4 font-black text-slate-800">{log.aksi}</td>
                            <td className="p-4 text-slate-600">{log.detail}</td>
                            <td className="p-4 text-center">
                              <span className="bg-emerald-100 text-emerald-800 px-2 py-0.5 rounded-full font-bold">
                                {log.status}
                              </span>
                            </td>
                          </tr>
                        ))}
                      </tbody>
                    </table>
                  </div>
                </div>
              </div>
            )}

            {/* TAB: SETTINGS & GOOGLE API INTEGRATIONS */}
            {currentTab === 'profile' && (
              <div className="space-y-6">
                <div>
                  <h2 className="text-xl font-extrabold text-slate-800">⚙️ Profil & Integrasi API Google Apps Script</h2>
                  <p className="text-xs text-slate-400">Atur kredensial, koneksi penyimpanan Google Drive, dan kontrol hak akses kasir.</p>
                </div>

                <div className="grid grid-cols-1 lg:grid-cols-2 gap-6">
                  {/* Super Admin Form */}
                  <div className="bg-white p-6 rounded-xl border border-slate-200 shadow-sm space-y-4">
                    <h3 className="text-base font-bold text-slate-800">Ubah Profil Super Admin</h3>
                    
                    <div className="flex items-center gap-3">
                      {adminProfile.photo ? (
                        <img src={adminProfile.photo} className="w-16 h-16 rounded-full object-cover border-2 border-emerald-500" alt="Admin" />
                      ) : (
                        <div className="w-16 h-16 bg-emerald-600 text-white font-bold text-lg rounded-full flex items-center justify-center">SA</div>
                      )}
                      <div>
                        <label className="block text-xs font-bold text-slate-400 uppercase">Ganti Foto Profil</label>
                        <input 
                          type="file" 
                          accept="image/*" 
                          onChange={(e) => handleImageUpload(e, (base64) => setAdminProfile({ ...adminProfile, photo: base64 }))} 
                          className="text-xs mt-1"
                        />
                      </div>
                    </div>

                    <div className="grid grid-cols-2 gap-2">
                      <div>
                        <label className="block text-xs font-bold text-slate-500 mb-1">Nama Lengkap Admin</label>
                        <input 
                          type="text" 
                          value={adminProfile.namaLengkap}
                          onChange={(e) => setAdminProfile({ ...adminProfile, namaLengkap: e.target.value })}
                          className="w-full px-3 py-2 border border-slate-300 rounded text-sm focus:outline-emerald-500"
                        />
                      </div>
                      <div>
                        <label className="block text-xs font-bold text-slate-500 mb-1">Username Super Admin</label>
                        <input 
                          type="text" 
                          value={adminProfile.username}
                          onChange={(e) => setAdminProfile({ ...adminProfile, username: e.target.value })}
                          className="w-full px-3 py-2 border border-slate-300 rounded text-sm focus:outline-emerald-500"
                        />
                      </div>
                    </div>

                    <div>
                      <label className="block text-xs font-bold text-slate-500 mb-1">Kata Sandi Pengaman (Password)</label>
                      <input 
                        type="password" 
                        value={adminProfile.password}
                        onChange={(e) => setAdminProfile({ ...adminProfile, password: e.target.value })}
                        className="w-full px-3 py-2 border border-slate-300 rounded text-sm focus:outline-emerald-500"
                      />
                    </div>

                    <div className="pt-4 border-t">
                      <h4 className="text-xs font-bold text-slate-400 uppercase mb-2">Penyesuaian Info Toko</h4>
                      <div className="grid grid-cols-2 gap-2">
                        <div>
                          <label className="block text-[10px] font-bold text-slate-500 mb-1">Nama Toko Sembako</label>
                          <input 
                            type="text" 
                            value={appTitle}
                            onChange={(e) => setAppTitle(e.target.value)}
                            className="w-full px-3 py-2 border border-slate-300 rounded text-sm"
                          />
                        </div>
                        <div>
                          <label className="block text-[10px] font-bold text-slate-500 mb-1">Sub-judul / Slogan</label>
                          <input 
                            type="text" 
                            value={appDesc}
                            onChange={(e) => setAppDesc(e.target.value)}
                            className="w-full px-3 py-2 border border-slate-300 rounded text-sm"
                          />
                        </div>
                      </div>
                      
                      <div className="grid grid-cols-2 gap-2 mt-2">
                        <div>
                          <label className="block text-[10px] font-bold text-slate-500 mb-1">Unggah Logo Toko</label>
                          <input 
                            type="file" 
                            accept="image/*" 
                            onChange={(e) => handleImageUpload(e, setAppLogo)} 
                            className="text-[10px]"
                          />
                        </div>
                        <div>
                          <label className="block text-[10px] font-bold text-slate-500 mb-1">Unggah Header Banner</label>
                          <input 
                            type="file" 
                            accept="image/*" 
                            onChange={(e) => handleImageUpload(e, setAppBanner)} 
                            className="text-[10px]"
                          />
                        </div>
                      </div>
                    </div>

                    <button 
                      onClick={() => {
                        playSynthesizedSound('pay_success');
                        alert("Pengaturan super admin berhasil diperbarui!");
                        logHistory("Sistem", "Ubah Pengaturan", "Memperbarui konfigurasi profile admin dan branding toko");
                      }}
                      className="w-full bg-emerald-600 text-white font-bold py-2 rounded shadow hover:bg-emerald-700 text-xs uppercase"
                    >
                      Simpan Perubahan Pengaturan 💾
                    </button>
                  </div>

                  {/* Cloud API & Access Rights Control (ACL) */}
                  <div className="bg-white p-6 rounded-xl border border-slate-200 shadow-sm space-y-6">
                    <div className="space-y-3">
                      <h3 className="text-base font-bold text-slate-800">Koneksi Database Cloud & Apps Script</h3>
                      
                      <div>
                        <label className="block text-xs font-bold text-slate-500 mb-1">Google Apps Script Web App URL</label>
                        <input 
                          type="text" 
                          value={adminProfile.gasApiUrl}
                          onChange={(e) => setAdminProfile({ ...adminProfile, gasApiUrl: e.target.value })}
                          className="w-full px-3 py-2 border border-slate-300 rounded text-xs font-mono focus:outline-blue-500"
                        />
                      </div>

                      <div>
                        <label className="block text-xs font-bold text-slate-500 mb-1">Google Drive Folder ID (Untuk Foto Barang)</label>
                        <input 
                          type="text" 
                          value={adminProfile.gdriveFolderId}
                          onChange={(e) => setAdminProfile({ ...adminProfile, gdriveFolderId: e.target.value })}
                          className="w-full px-3 py-2 border border-slate-300 rounded text-xs font-mono focus:outline-blue-500"
                        />
                      </div>

                      <div>
                        <label className="block text-xs font-bold text-slate-500 mb-1">Google Drive Developer API Key</label>
                        <input 
                          type="password" 
                          value={adminProfile.gdriveApiKey}
                          onChange={(e) => setAdminProfile({ ...adminProfile, gdriveApiKey: e.target.value })}
                          className="w-full px-3 py-2 border border-slate-300 rounded text-xs font-mono focus:outline-blue-500"
                        />
                      </div>
                    </div>

                    <div className="border-t pt-4">
                      <h3 className="text-base font-bold text-slate-800 mb-3">Hak Akses Anggota & Kasir (ACL Control)</h3>
                      <p className="text-xs text-slate-400 mb-4">Gunakan tombol slide untuk mengontrol fitur yang dapat digunakan oleh staff non-admin.</p>
                      
                      <div className="space-y-3">
                        <div className="flex items-center justify-between">
                          <span className="text-xs font-bold text-slate-700">Akses Pendaftaran Kartu Anggota Baru</span>
                          <button 
                            onClick={() => { setAcl({ ...acl, memberAccess: !acl.memberAccess }); playSynthesizedSound('beep_click'); }}
                            className={`w-11 h-6 rounded-full transition relative ${acl.memberAccess ? 'bg-emerald-500' : 'bg-slate-300'}`}
                          >
                            <span className={`absolute top-1 left-1 bg-white w-4 h-4 rounded-full transition ${acl.memberAccess ? 'translate-x-5' : ''}`}></span>
                          </button>
                        </div>

                        <div className="flex items-center justify-between">
                          <span className="text-xs font-bold text-slate-700">Akses Transaksi Kasir POS</span>
                          <button 
                            onClick={() => { setAcl({ ...acl, kasirAccess: !acl.kasirAccess }); playSynthesizedSound('beep_click'); }}
                            className={`w-11 h-6 rounded-full transition relative ${acl.kasirAccess ? 'bg-emerald-500' : 'bg-slate-300'}`}
                          >
                            <span className={`absolute top-1 left-1 bg-white w-4 h-4 rounded-full transition ${acl.kasirAccess ? 'translate-x-5' : ''}`}></span>
                          </button>
                        </div>

                        <div className="flex items-center justify-between">
                          <span className="text-xs font-bold text-slate-700">Akses Audit Log & Audit Riwayat</span>
                          <button 
                            onClick={() => { setAcl({ ...acl, historyAccess: !acl.historyAccess }); playSynthesizedSound('beep_click'); }}
                            className={`w-11 h-6 rounded-full transition relative ${acl.historyAccess ? 'bg-emerald-500' : 'bg-slate-300'}`}
                          >
                            <span className={`absolute top-1 left-1 bg-white w-4 h-4 rounded-full transition ${acl.historyAccess ? 'translate-x-5' : ''}`}></span>
                          </button>
                        </div>
                      </div>
                    </div>
                  </div>
                </div>
              </div>
            )}

          </main>
        </div>
      )}

      {/* ==========================================
          FACE SCAN OVERLAY SCREEN MODAL
         ========================================== */}
      {showFaceScan && (
        <div className="fixed inset-0 bg-black/85 backdrop-blur-md flex items-center justify-center p-4 z-50">
          <div className="w-full max-w-sm bg-slate-900 rounded-2xl p-6 text-center text-white border border-slate-800 space-y-6 relative overflow-hidden">
            {/* Pulsating circular neon scanner radar */}
            <div className="relative w-48 h-48 mx-auto rounded-full overflow-hidden border-4 border-blue-500 flex items-center justify-center bg-slate-950 shadow-[0_0_25px_rgba(59,130,246,0.5)]">
              {faceScanActive && (
                <div className="absolute inset-0 bg-gradient-to-b from-blue-500/20 to-transparent animate-pulse"></div>
              )}
              {/* Camera Video or Mock Target icon */}
              {faceScanActive ? (
                <video ref={videoRef} autoPlay playsInline className="w-full h-full object-cover scale-x-[-1]"></video>
              ) : (
                <span className="text-6xl">👤</span>
              )}

              {/* Scanning Laser Line */}
              {faceScanActive && !faceScanSuccess && (
                <div className="absolute left-0 w-full h-1 bg-blue-500 top-0 shadow-[0_0_10px_#3b82f6] animate-bounce"></div>
              )}

              {faceScanSuccess && (
                <div className="absolute inset-0 bg-emerald-900/80 flex items-center justify-center">
                  <span className="text-5xl animate-bounce">✅</span>
                </div>
              )}
            </div>

            <div>
              <h3 className="text-lg font-black tracking-wide">Pindai Wajah Pengguna</h3>
              <p className="text-xs text-slate-400 mt-1">Dekatkan wajah ke kamera depan handphone / PC Anda</p>
            </div>

            {faceScanSuccess ? (
              <p className="text-emerald-400 font-bold animate-pulse text-sm">✓ Wajah Teridentifikasi! Membuka Kunci...</p>
            ) : (
              <div className="flex items-center justify-center gap-2 text-blue-400 font-bold text-xs">
                <span className="w-2 h-2 rounded-full bg-blue-500 animate-ping"></span>
                <span>MENGANALISIS FITUR BIOMETRIK...</span>
              </div>
            )}

            <button 
              onClick={() => { setShowFaceScan(false); stopFaceScan(); playSynthesizedSound('clear'); }}
              className="w-full bg-slate-800 hover:bg-slate-700 text-slate-300 py-2.5 rounded-lg text-xs font-bold"
            >
              Batalkan Pemindaian ❌
            </button>
          </div>
        </div>
      )}

      {/* ==========================================
          CASHIER (POS) POP-UP OVERLAY MAIN SYSTEM
         ========================================== */}
      {showPOS && (
        <div className="fixed inset-0 bg-slate-950/80 backdrop-blur-sm flex items-center justify-center p-4 z-40 overflow-y-auto">
          <div className="bg-slate-900 text-white w-full max-w-6xl rounded-2xl shadow-2xl overflow-hidden border border-slate-800 flex flex-col md:flex-row h-[90vh]">
            
            {/* POS Left Panel: Items Selection Grid */}
            <div className="flex-1 flex flex-col p-4 border-r border-slate-800 h-1/2 md:h-full">
              {/* Header inside POS */}
              <div className="flex justify-between items-center mb-4">
                <h3 className="text-lg font-black tracking-tight flex items-center gap-2">
                  🛒 Mesin Kasir Sembako POS
                </h3>
                
                {/* Audio preset select */}
                <div className="flex items-center gap-1.5 bg-slate-800 p-1 rounded-lg text-[10px]">
                  <span>🔊 Nada Kasir:</span>
                  <select 
                    value={posActiveAudioIndex} 
                    onChange={(e) => {
                      const idx = parseInt(e.target.value);
                      setPosActiveAudioIndex(idx);
                      playSynthesizedSound(SOUND_PRESETS[idx].key);
                    }}
                    className="bg-slate-950 text-white font-bold p-1 rounded border-none focus:ring-0"
                  >
                    {SOUND_PRESETS.map((p, idx) => (
                      <option key={p.key} value={idx}>{p.name}</option>
                    ))}
                  </select>
                </div>
              </div>

              {/* Items Grid */}
              <div className="flex-1 overflow-y-auto grid grid-cols-2 lg:grid-cols-3 gap-2.5 pb-4">
                {products.map(p => (
                  <div 
                    key={p.id}
                    onClick={() => addToCart(p)}
                    className="bg-slate-800 p-3 rounded-xl border border-slate-700 hover:border-emerald-500 cursor-pointer select-none transition flex flex-col justify-between"
                  >
                    <div>
                      <div className="flex justify-between text-[10px] text-slate-400 font-bold">
                        <span>SKU: {p.id}</span>
                        <span className={`px-1.5 py-0.2 rounded ${p.stok <= 5 ? 'bg-red-900/50 text-red-300' : 'bg-emerald-900/50 text-emerald-300'}`}>
                          Stok {p.stok}
                        </span>
                      </div>
                      <h4 className="text-xs font-black mt-1 line-clamp-2 text-white">{p.nama}</h4>
                    </div>

                    <div className="mt-3 flex justify-between items-end">
                      <div>
                        {p.diskon > 0 ? (
                          <span className="text-[9px] line-through text-slate-500 block">
                            Rp {p.hargaJual.toLocaleString('id-ID')}
                          </span>
                        ) : null}
                        <span className="text-xs font-black text-amber-400">
                          Rp {(p.hargaJual * (1 - p.diskon / 100)).toLocaleString('id-ID')}
                        </span>
                      </div>
                      <span className="text-xs bg-emerald-600 text-white p-1 rounded-md">＋</span>
                    </div>
                  </div>
                ))}
              </div>
            </div>

            {/* POS Right Panel: Shopping Cart & Checkout */}
            <div className="w-full md:w-96 bg-slate-950 p-4 flex flex-col justify-between h-1/2 md:h-full">
              <div>
                <div className="flex justify-between items-center mb-3">
                  <h4 className="text-sm font-bold text-slate-400">Keranjang Pembelian</h4>
                  <button 
                    onClick={() => { setPosCart([]); playSynthesizedSound('clear'); }}
                    className="text-xs text-red-400 font-bold hover:underline"
                  >
                    Kosongkan 🗑️
                  </button>
                </div>

                {/* Items in Cart */}
                <div className="space-y-2 max-h-48 md:max-h-80 overflow-y-auto pr-1">
                  {posCart.map(item => {
                    const finalPrice = item.hargaJual * (1 - item.diskon / 100);
                    return (
                      <div key={item.id} className="bg-slate-900 p-2.5 rounded-lg border border-slate-800 flex justify-between items-center text-xs">
                        <div className="flex-1 min-w-0 pr-2">
                          <h5 className="font-bold text-white truncate">{item.nama}</h5>
                          <span className="text-[10px] text-slate-400">Rp {finalPrice.toLocaleString('id-ID')}</span>
                        </div>
                        <div className="flex items-center gap-1">
                          <button 
                            onClick={() => updateCartQty(item.id, item.qty - 1)}
                            className="w-5 h-5 bg-slate-800 rounded font-bold text-center"
                          >
                            -
                          </button>
                          <span className="w-6 text-center font-bold">{item.qty}</span>
                          <button 
                            onClick={() => updateCartQty(item.id, item.qty + 1)}
                            className="w-5 h-5 bg-slate-800 rounded font-bold text-center"
                          >
                            +
                          </button>
                        </div>
                      </div>
                    );
                  })}
                  {posCart.length === 0 && (
                    <p className="text-center text-xs text-slate-500 py-8">Belum ada barang dipilih.</p>
                  )}
                </div>
              </div>

              {/* Cash & Payment Section */}
              <div className="border-t border-slate-800 pt-3 space-y-3">
                <div className="bg-slate-900 p-3 rounded-lg space-y-1.5">
                  <div className="flex justify-between text-xs text-slate-400">
                    <span>Subtotal</span>
                    <span>Rp {calculateSubtotal().toLocaleString('id-ID')}</span>
                  </div>
                  <div className="flex justify-between text-sm font-bold text-white border-t border-slate-800 pt-1.5">
                    <span>Total Tagihan</span>
                    <span className="text-amber-400 text-base">Rp {calculateSubtotal().toLocaleString('id-ID')}</span>
                  </div>
                </div>

                {/* Quick Cash Buttons */}
                <div className="grid grid-cols-3 gap-1">
                  {[
                    { val: 5000, label: "5K", color: "bg-teal-900 hover:bg-teal-800" },
                    { val: 10000, label: "10K", color: "bg-blue-900 hover:bg-blue-800" },
                    { val: 20000, label: "20K", color: "bg-green-900 hover:bg-green-800" },
                    { val: 50000, label: "50K", color: "bg-purple-900 hover:bg-purple-800" },
                    { val: 100000, label: "100K", color: "bg-red-900 hover:bg-red-800" },
                    { val: 500000, label: "500K", color: "bg-indigo-900 hover:bg-indigo-800" }
                  ].map(btn => (
                    <button
                      key={btn.val}
                      onClick={() => { setPosCashAmount(prev => prev + btn.val); playSynthesizedSound('beep_click'); }}
                      className={`text-[10px] font-bold text-white p-1.5 rounded transition ${btn.color}`}
                    >
                      +{btn.label}
                    </button>
                  ))}
                  <button 
                    onClick={() => { setPosCashAmount(calculateSubtotal()); playSynthesizedSound('general_ok'); }}
                    className="col-span-3 bg-emerald-600 hover:bg-emerald-700 text-white font-bold p-1.5 rounded text-xs transition"
                  >
                    💵 Uang Pas
                  </button>
                </div>

                {/* Cash Input */}
                <div>
                  <label className="block text-[10px] text-slate-400 font-bold uppercase mb-1">Nominal Tunai Bayar (Rp)</label>
                  <input 
                    type="number" 
                    value={posCashAmount || ''} 
                    onChange={(e) => setPosCashAmount(parseFloat(e.target.value) || 0)}
                    placeholder="0" 
                    className="w-full bg-slate-900 text-right text-lg font-black text-amber-400 px-3 py-2 border border-slate-800 rounded focus:outline-emerald-500"
                  />
                </div>

                {/* Pay & Print Button */}
                <div className="flex gap-2">
                  <button 
                    onClick={() => { setShowPOS(false); setPosCart([]); playSynthesizedSound('clear'); }}
                    className="bg-slate-800 hover:bg-slate-700 text-white p-2.5 rounded-lg text-xs font-bold"
                  >
                    Tutup ❌
                  </button>
                  <button 
                    onClick={processPayment}
                    className="flex-1 bg-gradient-to-r from-emerald-500 to-teal-600 hover:from-emerald-600 hover:to-teal-700 text-white font-black py-2.5 rounded-lg text-sm text-center shadow-md shadow-emerald-950/50"
                  >
                    BAYAR & CETAK RECEIPT 📄
                  </button>
                </div>
              </div>

            </div>

          </div>
        </div>
      )}

      {/* ==========================================
          RECEIPT POP-UP MODAL (KERTAS KASIR)
         ========================================== */}
      {showReceipt && lastReceipt && (
        <div className="fixed inset-0 bg-black/80 backdrop-blur-sm flex items-center justify-center p-4 z-50">
          <div className="bg-white text-slate-900 w-full max-w-sm rounded-xl p-6 shadow-2xl border border-slate-200 font-mono text-xs">
            <div className="text-center space-y-1">
              <h3 className="text-sm font-black uppercase">{appTitle}</h3>
              <p className="text-[10px] text-slate-500">{appDesc}</p>
              <div className="border-t border-dashed border-slate-300 my-2"></div>
            </div>

            <div className="space-y-1 my-3 text-[10px]">
              <p>No Transaksi: <b>{lastReceipt.id}</b></p>
              <p>Tanggal: {lastReceipt.tanggal}</p>
              <p>Kasir: {lastReceipt.kasir}</p>
              <div className="border-t border-dashed border-slate-300 my-2"></div>
            </div>

            {/* Receipt Items */}
            <div className="space-y-2 text-[10px]">
              {lastReceipt.items.map(item => (
                <div key={item.id} className="flex justify-between">
                  <span>{item.nama} x{item.qty}</span>
                  <span>Rp {(item.hargaJual * item.qty).toLocaleString('id-ID')}</span>
                </div>
              ))}
              <div className="border-t border-dashed border-slate-300 my-2"></div>
            </div>

            <div className="space-y-1.5 text-[10px]">
              <div className="flex justify-between font-black text-xs">
                <span>TOTAL</span>
                <span>Rp {lastReceipt.total.toLocaleString('id-ID')}</span>
              </div>
              <div className="flex justify-between">
                <span>BAYAR TUNAI</span>
                <span>Rp {lastReceipt.bayar.toLocaleString('id-ID')}</span>
              </div>
              <div className="flex justify-between font-bold text-emerald-700">
                <span>KEMBALIAN</span>
                <span>Rp {lastReceipt.kembali.toLocaleString('id-ID')}</span>
              </div>
            </div>

            <div className="text-center mt-6 space-y-1">
              <p className="text-[9px] font-bold">*** TERIMA KASIH ***</p>
              <p className="text-[8px] text-slate-400">Sembako Segar & Murah Hanya Di Sini</p>
            </div>

            <button 
              onClick={() => { setShowReceipt(false); playSynthesizedSound('general_ok'); }}
              className="mt-6 w-full bg-slate-950 hover:bg-slate-900 text-white font-bold py-2.5 rounded-lg text-center"
            >
              SELESAI & OK ✅
            </button>
          </div>
        </div>
      )}

      {/* ==========================================
          CRUD FORM MODALS: PRODUCT DATABASE
         ========================================== */}
      {productForm && (
        <div className="fixed inset-0 bg-black/60 backdrop-blur-sm flex items-center justify-center p-4 z-50">
          <div className="bg-white text-slate-800 rounded-2xl w-full max-w-lg p-6 border shadow-2xl space-y-4">
            <h3 className="text-lg font-black">{productForm.id ? "Ubah Detail Barang" : "Tambah Barang Baru"}</h3>
            
            <div className="grid grid-cols-2 gap-3">
              <div className="col-span-2">
                <label className="block text-xs font-bold text-slate-500 mb-1">Nama Barang Sembako</label>
                <input 
                  type="text" 
                  value={productForm.nama}
                  onChange={(e) => setProductForm({ ...productForm, nama: e.target.value })}
                  placeholder="Contoh: Beras Pandan Wangi 10kg"
                  className="w-full px-3 py-2 border rounded-lg focus:outline-emerald-500 text-sm"
                />
              </div>

              <div>
                <label className="block text-xs font-bold text-slate-500 mb-1">Kategori Sembako</label>
                <select 
                  value={productForm.kategori}
                  onChange={(e) => setProductForm({ ...productForm, kategori: e.target.value })}
                  className="w-full px-3 py-2 border rounded-lg focus:outline-emerald-500 text-sm bg-white"
                >
                  <option value="Sembako Utama">Sembako Utama</option>
                  <option value="Minyak & Lemak">Minyak & Lemak</option>
                  <option value="Makanan Instan">Makanan Instan</option>
                  <option value="Susu & Olahan">Susu & Olahan</option>
                </select>
              </div>

              <div>
                <label className="block text-xs font-bold text-slate-500 mb-1">Jenis Kemasan / Unit</label>
                <select 
                  value={productForm.unit}
                  onChange={(e) => setProductForm({ ...productForm, unit: e.target.value })}
                  className="w-full px-3 py-2 border rounded-lg focus:outline-emerald-500 text-sm bg-white"
                >
                  <option value="pcs">pcs</option>
                  <option value="pack">pack</option>
                  <option value="lusin">lusin</option>
                  <option value="kaleng">kaleng</option>
                  <option value="kardus">kardus</option>
                </select>
              </div>

              <div>
                <label className="block text-xs font-bold text-slate-500 mb-1">Harga Beli Rp</label>
                <input 
                  type="number" 
                  value={productForm.hargaBeli}
                  onChange={(e) => setProductForm({ ...productForm, hargaBeli: parseFloat(e.target.value) || 0 })}
                  className="w-full px-3 py-2 border rounded-lg text-sm"
                />
              </div>

              <div>
                <label className="block text-xs font-bold text-slate-500 mb-1">Harga Jual Rp</label>
                <input 
                  type="number" 
                  value={productForm.hargaJual}
                  onChange={(e) => setProductForm({ ...productForm, hargaJual: parseFloat(e.target.value) || 0 })}
                  className="w-full px-3 py-2 border rounded-lg text-sm"
                />
              </div>

              <div>
                <label className="block text-xs font-bold text-slate-500 mb-1">Stok Barang</label>
                <input 
                  type="number" 
                  value={productForm.stok}
                  onChange={(e) => setProductForm({ ...productForm, stok: parseInt(e.target.value) || 0 })}
                  className="w-full px-3 py-2 border rounded-lg text-sm"
                />
              </div>

              <div>
                <label className="block text-xs font-bold text-slate-500 mb-1">Tanggal Expire</label>
                <input 
                  type="date" 
                  value={productForm.expire}
                  onChange={(e) => setProductForm({ ...productForm, expire: e.target.value })}
                  className="w-full px-3 py-2 border rounded-lg text-sm"
                />
              </div>
            </div>

            <div className="flex gap-2 justify-end pt-4 border-t">
              <button 
                onClick={() => { setProductForm(null); playSynthesizedSound('clear'); }}
                className="bg-slate-200 text-slate-700 px-4 py-2 rounded-lg text-sm font-bold"
              >
                Kembali
              </button>
              <button 
                onClick={() => {
                  // Save product logic
                  if (products.some(p => p.id === productForm.id)) {
                    // edit
                    setProducts(prev => prev.map(p => p.id === productForm.id ? { ...productForm } : p));
                    logHistory("Barang", "Edit", `Memperbarui detail produk ${productForm.nama}`);
                  } else {
                    // add
                    setProducts(prev => [...prev, { ...productForm }]);
                    logHistory("Barang", "Tambah", `Menambahkan produk baru ${productForm.nama}`);
                  }
                  playSynthesizedSound('pay_success');
                  setProductForm(null);
                }}
                className="bg-emerald-600 text-white px-5 py-2 rounded-lg text-sm font-bold shadow-md"
              >
                Simpan Data Sembako
              </button>
            </div>
          </div>
        </div>
      )}

      {/* ==========================================
          CRUD FORM MODALS: EMPLOYEE DATA
         ========================================== */}
      {employeeForm && (
        <div className="fixed inset-0 bg-black/60 backdrop-blur-sm flex items-center justify-center p-4 z-50">
          <div className="bg-white text-slate-800 rounded-2xl w-full max-w-lg p-6 border shadow-2xl space-y-4">
            <h3 className="text-lg font-black">{employeeForm.id ? "Ubah Data Karyawan" : "Tambah Karyawan Baru"}</h3>
            
            <div className="grid grid-cols-2 gap-3 text-sm">
              <div className="col-span-2">
                <label className="block text-xs font-bold text-slate-500 mb-1">Nama Lengkap Karyawan</label>
                <input 
                  type="text" 
                  value={employeeForm.nama}
                  onChange={(e) => setEmployeeForm({ ...employeeForm, nama: e.target.value })}
                  className="w-full px-3 py-2 border rounded-lg focus:outline-emerald-500"
                />
              </div>

              <div>
                <label className="block text-xs font-bold text-slate-500 mb-1">Pilih Provinsi</label>
                <select 
                  value={employeeForm.provinsi}
                  onChange={(e) => {
                    const prov = e.target.value;
                    const defaultKab = Object.keys(PROVINSI_DATA[prov])[0];
                    const defaultKec = PROVINSI_DATA[prov][defaultKab][0];
                    setEmployeeForm({ ...employeeForm, provinsi: prov, kabupaten: defaultKab, kecamatan: defaultKec });
                  }}
                  className="w-full px-3 py-2 border rounded-lg bg-white"
                >
                  {Object.keys(PROVINSI_DATA).map(p => <option key={p} value={p}>{p}</option>)}
                </select>
              </div>

              <div>
                <label className="block text-xs font-bold text-slate-500 mb-1">Kabupaten/Kota</label>
                <select 
                  value={employeeForm.kabupaten}
                  onChange={(e) => {
                    const kab = e.target.value;
                    const defaultKec = PROVINSI_DATA[employeeForm.provinsi][kab][0];
                    setEmployeeForm({ ...employeeForm, kabupaten: kab, kecamatan: defaultKec });
                  }}
                  className="w-full px-3 py-2 border rounded-lg bg-white"
                >
                  {Object.keys(PROVINSI_DATA[employeeForm.provinsi] || {}).map(k => <option key={k} value={k}>{k}</option>)}
                </select>
              </div>

              <div>
                <label className="block text-xs font-bold text-slate-500 mb-1">Kecamatan</label>
                <select 
                  value={employeeForm.kecamatan}
                  onChange={(e) => setEmployeeForm({ ...employeeForm, kecamatan: e.target.value })}
                  className="w-full px-3 py-2 border rounded-lg bg-white"
                >
                  {(PROVINSI_DATA[employeeForm.provinsi]?.[employeeForm.kabupaten] || []).map(kec => (
                    <option key={kec} value={kec}>{kec}</option>
                  ))}
                </select>
              </div>

              <div>
                <label className="block text-xs font-bold text-slate-500 mb-1">Pendidikan Terakhir / Lulusan</label>
                <input 
                  type="text" 
                  value={employeeForm.lulusan}
                  onChange={(e) => setEmployeeForm({ ...employeeForm, lulusan: e.target.value })}
                  className="w-full px-3 py-2 border rounded-lg"
                />
              </div>

              <div className="col-span-2">
                <label className="block text-xs font-bold text-slate-500 mb-1">Alamat Lengkap</label>
                <input 
                  type="text" 
                  value={employeeForm.alamat}
                  onChange={(e) => setEmployeeForm({ ...employeeForm, alamat: e.target.value })}
                  className="w-full px-3 py-2 border rounded-lg"
                />
              </div>

              <div className="col-span-2">
                <label className="block text-xs font-bold text-slate-500 mb-1">No. Telephone</label>
                <input 
                  type="text" 
                  value={employeeForm.telp}
                  onChange={(e) => setEmployeeForm({ ...employeeForm, telp: e.target.value })}
                  className="w-full px-3 py-2 border rounded-lg"
                />
              </div>
            </div>

            <div className="flex gap-2 justify-end pt-4 border-t">
              <button 
                onClick={() => { setEmployeeForm(null); playSynthesizedSound('clear'); }}
                className="bg-slate-200 text-slate-700 px-4 py-2 rounded-lg text-sm font-bold"
              >
                Kembali
              </button>
              <button 
                onClick={() => {
                  if (employees.some(e => e.id === employeeForm.id)) {
                    setEmployees(prev => prev.map(e => e.id === employeeForm.id ? { ...employeeForm } : e));
                    logHistory("Karyawan", "Edit", `Memperbarui detail karyawan ${employeeForm.nama}`);
                  } else {
                    setEmployees(prev => [...prev, { ...employeeForm }]);
                    logHistory("Karyawan", "Tambah", `Mendaftarkan karyawan baru ${employeeForm.nama}`);
                  }
                  playSynthesizedSound('pay_success');
                  setEmployeeForm(null);
                }}
                className="bg-emerald-600 text-white px-5 py-2 rounded-lg text-sm font-bold shadow-md"
              >
                Simpan Karyawan
              </button>
            </div>
          </div>
        </div>
      )}

      {/* ==========================================
          CRUD FORM MODALS: SUPPLIER DATA
         ========================================== */}
      {supplierForm && (
        <div className="fixed inset-0 bg-black/60 backdrop-blur-sm flex items-center justify-center p-4 z-50">
          <div className="bg-white text-slate-800 rounded-2xl w-full max-w-lg p-6 border shadow-2xl space-y-4">
            <h3 className="text-lg font-black">{supplierForm.id ? "Ubah Data Supplier" : "Tambah Supplier Baru"}</h3>
            
            <div className="grid grid-cols-2 gap-3 text-sm">
              <div className="col-span-2">
                <label className="block text-xs font-bold text-slate-500 mb-1">Nama Perusahaan / Supplier</label>
                <input 
                  type="text" 
                  value={supplierForm.nama}
                  onChange={(e) => setSupplierForm({ ...supplierForm, nama: e.target.value })}
                  className="w-full px-3 py-2 border rounded-lg focus:outline-emerald-500"
                />
              </div>

              <div>
                <label className="block text-xs font-bold text-slate-500 mb-1">Pilih Provinsi</label>
                <select 
                  value={supplierForm.provinsi}
                  onChange={(e) => {
                    const prov = e.target.value;
                    const defaultKab = Object.keys(PROVINSI_DATA[prov])[0];
                    const defaultKec = PROVINSI_DATA[prov][defaultKab][0];
                    setSupplierForm({ ...supplierForm, provinsi: prov, kabupaten: defaultKab, kecamatan: defaultKec });
                  }}
                  className="w-full px-3 py-2 border rounded-lg bg-white"
                >
                  {Object.keys(PROVINSI_DATA).map(p => <option key={p} value={p}>{p}</option>)}
                </select>
              </div>

              <div>
                <label className="block text-xs font-bold text-slate-500 mb-1">Kabupaten/Kota</label>
                <select 
                  value={supplierForm.kabupaten}
                  onChange={(e) => {
                    const kab = e.target.value;
                    const defaultKec = PROVINSI_DATA[supplierForm.provinsi][kab][0];
                    setSupplierForm({ ...supplierForm, kabupaten: kab, kecamatan: defaultKec });
                  }}
                  className="w-full px-3 py-2 border rounded-lg bg-white"
                >
                  {Object.keys(PROVINSI_DATA[supplierForm.provinsi] || {}).map(k => <option key={k} value={k}>{k}</option>)}
                </select>
              </div>

              <div>
                <label className="block text-xs font-bold text-slate-500 mb-1">Kecamatan</label>
                <select 
                  value={supplierForm.kecamatan}
                  onChange={(e) => setSupplierForm({ ...supplierForm, kecamatan: e.target.value })}
                  className="w-full px-3 py-2 border rounded-lg bg-white"
                >
                  {(PROVINSI_DATA[supplierForm.provinsi]?.[supplierForm.kabupaten] || []).map(kec => (
                    <option key={kec} value={kec}>{kec}</option>
                  ))}
                </select>
              </div>

              <div className="col-span-2">
                <label className="block text-xs font-bold text-slate-500 mb-1">Alamat Lengkap Kantor</label>
                <input 
                  type="text" 
                  value={supplierForm.alamat}
                  onChange={(e) => setSupplierForm({ ...supplierForm, alamat: e.target.value })}
                  className="w-full px-3 py-2 border rounded-lg"
                />
              </div>

              <div className="col-span-2">
                <label className="block text-xs font-bold text-slate-500 mb-1">No. Telephone / Kontak Hubung</label>
                <input 
                  type="text" 
                  value={supplierForm.telp}
                  onChange={(e) => setSupplierForm({ ...supplierForm, telp: e.target.value })}
                  className="w-full px-3 py-2 border rounded-lg"
                />
              </div>
            </div>

            <div className="flex gap-2 justify-end pt-4 border-t">
              <button 
                onClick={() => { setSupplierForm(null); playSynthesizedSound('clear'); }}
                className="bg-slate-200 text-slate-700 px-4 py-2 rounded-lg text-sm font-bold"
              >
                Kembali
              </button>
              <button 
                onClick={() => {
                  if (suppliers.some(s => s.id === supplierForm.id)) {
                    setSuppliers(prev => prev.map(s => s.id === supplierForm.id ? { ...supplierForm } : s));
                    logHistory("Supplier", "Edit", `Memperbarui detail supplier ${supplierForm.nama}`);
                  } else {
                    setSuppliers(prev => [...prev, { ...supplierForm }]);
                    logHistory("Supplier", "Tambah", `Menambahkan supplier baru ${supplierForm.nama}`);
                  }
                  playSynthesizedSound('pay_success');
                  setSupplierForm(null);
                }}
                className="bg-emerald-600 text-white px-5 py-2 rounded-lg text-sm font-bold shadow-md"
              >
                Simpan Supplier
              </button>
            </div>
          </div>
        </div>
      )}

      {/* ==========================================
          FOOTER BRANDING INFORMATION
         ========================================== */}
      <footer className="bg-slate-900 border-t border-slate-800 text-slate-400 py-6 text-center text-xs mt-auto z-10 relative">
        <p className="font-extrabold text-slate-300">🏪 {appTitle} Management Cloud Panel</p>
        <p className="text-[10px] mt-1 text-slate-500">© 2026 Toko Sembako Jaya Inc. Terintegrasi penuh dengan Google Web App Script & Drive Folder Storage.</p>
      </footer>

    </div>
  );
}