import React, { useState } from "react";

// Single-file React component for a simple IPM (Ikatan Pelajar Muhammadiyah) organization website
// Tailwind CSS required for styling. Drop this component into a React app (Vite / CRA / Next) with Tailwind set up.

export default function IPMWebsite() {
  const [menuOpen, setMenuOpen] = useState(false);

  const programs = [
    {
      title: "Pelatihan Kepemimpinan",
      desc: "Mengasah kemampuan kepemimpinan pelajar melalui workshop dan mentoring.",
    },
    {
      title: "Bakti Sosial",
      desc: "Kegiatan sosial di komunitas: donor darah, bersih-bersih, pembagian sembako.",
    },
    {
      title: "Kajian & Pengajian",
      desc: "Kajian rutin dengan tema pendidikan, akhlak, dan pengembangan diri.",
    },
  ];

  const events = [
    { date: "2025-12-10", title: "Musyawarah Komisariat", place: "Aula SMP Muhammadiyah" },
    { date: "2026-01-14", title: "Pelatihan Kepemimpinan Dasar", place: "Gedung Serbaguna" },
  ];

  return (
    <div className="min-h-screen bg-gray-50 text-gray-800"> 
      {/* NAV */}
      <header className="bg-white shadow">
        <div className="container mx-auto px-6 py-4 flex items-center justify-between">
          <div className="flex items-center space-x-3">
            <img src="/logo-ipm.png" alt="IPM Logo" className="w-12 h-12 object-cover rounded-md" />
            <div>
              <h1 className="text-lg font-bold">IPM - Ikatan Pelajar Muhammadiyah</h1>
              <p className="text-sm text-gray-500">Berkarya, Berakhlaqul Karimah, Berkemajuan</p>
            </div>
          </div>

          <nav className="hidden md:flex items-center space-x-6">
            <a href="#about" className="hover:text-indigo-600">Tentang</a>
            <a href="#programs" className="hover:text-indigo-600">Program</a>
            <a href="#events" className="hover:text-indigo-600">Kegiatan</a>
            <a href="#contact" className="hover:text-indigo-600">Kontak</a>
            <a href="#join" className="px-4 py-2 bg-indigo-600 text-white rounded-md shadow hover:opacity-95">Gabung</a>
          </nav>

          <button
            className="md:hidden p-2 rounded-md bg-gray-100"
            onClick={() => setMenuOpen(!menuOpen)}
            aria-label="Toggle menu"
          >
            <svg xmlns="http://www.w3.org/2000/svg" className="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
              <path strokeLinecap="round" strokeLinejoin="round" strokeWidth="2" d={menuOpen ? "M6 18L18 6M6 6l12 12" : "M4 6h16M4 12h16M4 18h16"} />
            </svg>
          </button>
        </div>

        {menuOpen && (
          <div className="md:hidden bg-white border-t">
            <div className="container mx-auto px-6 py-4 flex flex-col space-y-3">
              <a href="#about" onClick={() => setMenuOpen(false)}>Tentang</a>
              <a href="#programs" onClick={() => setMenuOpen(false)}>Program</a>
              <a href="#events" onClick={() => setMenuOpen(false)}>Kegiatan</a>
              <a href="#contact" onClick={() => setMenuOpen(false)}>Kontak</a>
              <a href="#join" className="inline-block px-4 py-2 bg-indigo-600 text-white rounded-md w-max" onClick={() => setMenuOpen(false)}>Gabung</a>
            </div>
          </div>
        )}
      </header>

      {/* HERO */}
      <section className="container mx-auto px-6 py-16 flex flex-col md:flex-row items-center gap-10">
        <div className="md:w-1/2">
          <h2 className="text-3xl md:text-4xl font-extrabold leading-tight">Bersama Membangun Pelajar yang Berintegritas</h2>
          <p className="mt-4 text-gray-600">IPM hadir untuk mengembangkan kemampuan kepemimpinan, keilmuan, dan sosial pelajar. Bergabunglah dan jadi bagian perubahan positif di sekolah dan lingkunganmu.</p>

          <div className="mt-6 flex gap-3">
            <a href="#join" className="px-5 py-3 bg-indigo-600 text-white rounded-md shadow">Gabung Sekarang</a>
            <a href="#programs" className="px-5 py-3 border rounded-md">Lihat Program</a>
          </div>
        </div>

        <div className="md:w-1/2">
          <div className="rounded-xl overflow-hidden shadow-lg">
            <img src="https://images.unsplash.com/photo-1524324463413-6f9f7b9a9b3b?auto=format&fit=crop&w=1400&q=60" alt="ipm hero" className="w-full h-72 object-cover" />
          </div>
        </div>
      </section>

      {/* ABOUT */}
      <section id="about" className="bg-white py-12">
        <div className="container mx-auto px-6">
          <h3 className="text-2xl font-bold">Tentang IPM</h3>
          <p className="mt-3 text-gray-600">IPM (Ikatan Pelajar Muhammadiyah) adalah organisasi pelajar yang bergerak di bidang pendidikan, pengembangan karakter, dan kegiatan sosial. Visi kami: mencetak generasi pelajar berakhlak dan berdaya saing.</p>

          <div className="mt-6 grid md:grid-cols-3 gap-6">
            <div className="p-4 border rounded-lg">
              <h4 className="font-semibold">Visi</h4>
              <p className="text-sm text-gray-600 mt-2">Menjadi wadah pembinaan pelajar berintegritas dan berdaya saing.</p>
            </div>
            <div className="p-4 border rounded-lg">
              <h4 className="font-semibold">Misi</h4>
              <ul className="text-sm text-gray-600 mt-2 list-disc list-inside">
                <li>Meningkatkan kualitas kepemimpinan pelajar.</li>
                <li>Mendorong kegiatan sosial kemasyarakatan.</li>
                <li>Membina nilai-nilai religius dan akademik.</li>
              </ul>
            </div>
            <div className="p-4 border rounded-lg">
              <h4 className="font-semibold">Nilai</h4>
              <p className="text-sm text-gray-600 mt-2">Kejujuran, tanggung jawab, solidaritas, dan inovasi.</p>
            </div>
          </div>
        </div>
      </section>

      {/* PROGRAMS */}
      <section id="programs" className="py-12">
        <div className="container mx-auto px-6">
          <h3 className="text-2xl font-bold">Program Unggulan</h3>
          <div className="mt-6 grid md:grid-cols-3 gap-6">
            {programs.map((p) => (
              <div key={p.title} className="p-6 bg-white rounded-lg shadow-sm">
                <h4 className="font-semibold text-lg">{p.title}</h4>
                <p className="text-sm mt-3 text-gray-600">{p.desc}</p>
                <button className="mt-4 inline-block text-indigo-600 underline">Selengkapnya</button>
              </div>
            ))}
          </div>
        </div>
      </section>

      {/* EVENTS */}
      <section id="events" className="bg-white py-12">
        <div className="container mx-auto px-6">
          <h3 className="text-2xl font-bold">Agenda & Kegiatan</h3>
          <div className="mt-6 grid md:grid-cols-2 gap-6">
            {events.map((e) => (
              <div key={e.title} className="p-4 border rounded-lg">
                <div className="flex justify-between items-start">
                  <div>
                    <h4 className="font-semibold">{e.title}</h4>
                    <p className="text-sm text-gray-600">{e.place}</p>
                  </div>
                  <div className="text-sm text-gray-500">{e.date}</div>
                </div>
              </div>
            ))}
          </div>
        </div>
      </section>

      {/* JOIN */}
      <section id="join" className="py-12">
        <div className="container mx-auto px-6 md:flex items-center gap-8">
          <div className="md:w-2/3">
            <h3 className="text-2xl font-bold">Ingin Bergabung?</h3>
            <p className="text-gray-600 mt-2">Isi formulir pendaftaran singkat dan tim kami akan menghubungi kamu untuk proses selanjutnya.</p>
          </div>
          <form className="mt-6 md:mt-0 md:w-1/3 bg-white p-4 rounded-lg shadow-sm">
            <label className="block text-sm">Nama</label>
            <input className="w-full mt-1 p-2 border rounded" placeholder="Nama lengkap" />
            <label className="block text-sm mt-3">Sekolah</label>
            <input className="w-full mt-1 p-2 border rounded" placeholder="Nama sekolah" />
            <label className="block text-sm mt-3">No. WA</label>
            <input className="w-full mt-1 p-2 border rounded" placeholder="08xx..." />
            <button type="button" className="mt-4 w-full px-4 py-2 bg-indigo-600 text-white rounded">Kirim</button>
          </form>
        </div>
      </section>

      {/* CONTACT */}
      <footer id="contact" className="bg-gray-900 text-white py-12">
        <div className="container mx-auto px-6 grid md:grid-cols-3 gap-6">
          <div>
            <h4 className="font-bold">IPM - Komisariat</h4>
            <p className="text-sm text-gray-300 mt-2">Alamat sekolah / kontak sekretariat.</p>
          </div>

          <div>
            <h4 className="font-bold">Ikuti Kami</h4>
            <ul className="text-sm text-gray-300 mt-2 space-y-2">
              <li>Instagram: @ipm_komisariat</li>
              <li>Facebook: IPM Komisariat</li>
              <li>WA: 08xx-xxxx-xxxx</li>
            </ul>
          </div>

          <div>
            <h4 className="font-bold">Newsletter</h4>
            <p className="text-sm text-gray-300 mt-2">Masukkan email untuk mendapatkan update kegiatan.</p>
            <div className="mt-3 flex gap-2">
              <input placeholder="Email kamu" className="p-2 rounded text-gray-800" />
              <button className="px-3 py-2 bg-indigo-600 rounded">Daftar</button>
            </div>
          </div>
        </div>

        <div className="mt-8 text-center text-gray-400 text-sm">© {new Date().getFullYear()} IPM - Komisariat. All rights reserved.</div>
      </footer>
    </div>
  );
}
