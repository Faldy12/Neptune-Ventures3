import { Button } from "@/components/ui/button";
import { useState } from "react";

export default function Home() {
  const [user, setUser] = useState(null);
  const [showLogin, setShowLogin] = useState(false);
  const [email, setEmail] = useState("");
  const [password, setPassword] = useState("");

  const handleLogin = () => {
    if (email === "admin@neptune.com" && password === "admin123") {
      setUser({ name: "Admin" });
      setShowLogin(false);
    } else {
      alert("Email atau password salah");
    }
  };

  return (
    <main className="min-h-screen bg-white text-gray-800">
      {/* Hero Section */}
      <section className="bg-blue-700 text-white py-20 px-6 text-center">
        <h1 className="text-4xl md:text-5xl font-bold mb-2">
          Agen Tiket Kapal & Sewa Speedboat Wisata
        </h1>
        <p className="text-xl font-medium text-yellow-300 mb-4">
          Neptune Ventures
        </p>
        <p className="mb-6">
          Tiket Kapal Pelni & DLU ke Berbagai Rute <br />
          Sewa Speedboat untuk Mancing, Snorkeling & Diving
        </p>
        <div className="flex justify-center gap-4">
          <Button className="bg-yellow-400 text-black hover:bg-yellow-300">
            PESAN SEKARANG
          </Button>
          <Button variant="outline" className="text-white border-white">
            LIHAT LAYANAN
          </Button>
        </div>
        {!user ? (
          <div className="mt-6">
            <Button
              className="bg-white text-blue-700 hover:bg-gray-100"
              onClick={() => setShowLogin(true)}
            >
              Admin Login
            </Button>
          </div>
        ) : (
          <p className="mt-4 text-sm">Login sebagai {user.name}</p>
        )}
      </section>

      {showLogin && (
        <section className="py-10 px-6 bg-yellow-50 text-center">
          <h2 className="text-2xl font-semibold mb-4">Login Admin</h2>
          <input
            type="email"
            placeholder="Email"
            value={email}
            onChange={(e) => setEmail(e.target.value)}
            className="border p-2 rounded mb-2 w-64"
          />
          <br />
          <input
            type="password"
            placeholder="Password"
            value={password}
            onChange={(e) => setPassword(e.target.value)}
            className="border p-2 rounded mb-4 w-64"
          />
          <br />
          <Button onClick={handleLogin} className="bg-blue-700 text-white">
            Login
          </Button>
        </section>
      )}

      {/* Tentang Kami */}
      <section className="py-16 px-6 max-w-4xl mx-auto">
        <h2 className="text-3xl font-semibold text-blue-700 mb-4">Tentang Kami</h2>
        <p>
          Kami adalah agen tiket resmi Pelni dan DLU, serta penyedia jasa sewa speedboat
          wisata di kawasan laut Indonesia timur. Dengan pelayanan ramah dan harga bersaing,
          <strong> Neptune Ventures </strong> siap menemani perjalanan laut Anda.
        </p>
      </section>

      {/* Layanan */}
      <section className="bg-gray-50 py-16 px-6">
        <h2 className="text-3xl font-semibold text-blue-700 text-center mb-10">
          Layanan Kami
        </h2>
        <div className="grid md:grid-cols-3 gap-8 max-w-6xl mx-auto">
          <div className="bg-white p-6 rounded-2xl shadow-md">
            <h3 className="text-xl font-bold mb-2">Tiket Kapal Pelni</h3>
            <p>Dapatkan tiket kapal Pelni untuk berbagai rute laut Indonesia.</p>
          </div>
          <div className="bg-white p-6 rounded-2xl shadow-md">
            <h3 className="text-xl font-bold mb-2">Tiket Kapal DLU</h3>
            <p>Pemesanan tiket kapal Dharma Lautan Utama (DLU) dengan mudah.</p>
          </div>
          <div className="bg-white p-6 rounded-2xl shadow-md">
            <h3 className="text-xl font-bold mb-2">Sewa Speedboat</h3>
            <p>
              Sewa speedboat untuk mancing, snorkeling, atau diving bersama teman dan keluarga.
            </p>
          </div>
        </div>
      </section>

      {/* Jadwal & Harga */}
      <section className="py-16 px-6 max-w-6xl mx-auto">
        <h2 className="text-3xl font-semibold text-blue-700 text-center mb-10">
          Jadwal & Harga
        </h2>
        <div className="overflow-auto">
          <table className="min-w-full bg-white border border-gray-300">
            <thead>
              <tr className="bg-blue-100">
                <th className="text-left py-2 px-4 border">Layanan</th>
                <th className="text-left py-2 px-4 border">Rute / Lokasi</th>
                <th className="text-left py-2 px-4 border">Jadwal</th>
                <th className="text-left py-2 px-4 border">Harga</th>
              </tr>
            </thead>
            <tbody>
              <tr>
                <td className="py-2 px-4 border">Kapal Pelni</td>
                <td className="py-2 px-4 border">Makassar - Ambon</td>
                <td className="py-2 px-4 border">Setiap Selasa</td>
                <td className="py-2 px-4 border">Rp 350.000</td>
              </tr>
              <tr>
                <td className="py-2 px-4 border">Kapal DLU</td>
                <td className="py-2 px-4 border">Surabaya - Labuan Bajo</td>
                <td className="py-2 px-4 border">Setiap Jumat</td>
                <td className="py-2 px-4 border">Rp 450.000</td>
              </tr>
              <tr>
                <td className="py-2 px-4 border">Speedboat Snorkeling</td>
                <td className="py-2 px-4 border">Pulau Samalona</td>
                <td className="py-2 px-4 border">Setiap Hari</td>
                <td className="py-2 px-4 border">Rp 1.200.000 / trip</td>
              </tr>
              <tr>
                <td className="py-2 px-4 border">Speedboat Diving</td>
                <td className="py-2 px-4 border">Pulau Kodingareng Keke</td>
                <td className="py-2 px-4 border">Setiap Sabtu & Minggu</td>
                <td className="py-2 px-4 border">Rp 1.500.000 / trip</td>
              </tr>
            </tbody>
          </table>
        </div>
      </section>

      {/* Galeri Foto */}
      <section className="py-16 px-6 max-w-6xl mx-auto">
        <h2 className="text-3xl font-semibold text-blue-700 text-center mb-10">
          Galeri Kegiatan
        </h2>
        <div className="grid grid-cols-2 md:grid-cols-4 gap-4">
          <div className="aspect-square bg-blue-100 rounded-xl"></div>
          <div className="aspect-square bg-blue-100 rounded-xl"></div>
          <div className="aspect-square bg-blue-100 rounded-xl"></div>
          <div className="aspect-square bg-blue-100 rounded-xl"></div>
        </div>
      </section>

      {/* Kontak */}
      <section className="bg-blue-50 py-16 px-6 text-center">
        <h2 className="text-3xl font-semibold text-blue-700 mb-4">Hubungi Kami</h2>
        <p className="mb-6">Untuk pemesanan tiket atau sewa speedboat, silakan hubungi kami melalui WhatsApp.</p>
        <Button className="bg-green-500 text-white text-lg hover:bg-green-600">
          Hubungi via WhatsApp
        </Button>
      </section>
    </main>
  );
}
# Neptune-Ventures3
