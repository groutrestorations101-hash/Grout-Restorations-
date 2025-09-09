# Grout-Restorations-
Grout restorations site
"use client";

import React from "react";
import { motion } from "framer-motion";
import { Phone, Calendar, ShieldCheck, Sparkles, Hammer, Droplets, Ruler, CheckCircle2, Star, Quote, Mail, MapPin, Clock, Facebook, Instagram } from "lucide-react";

// ✅ This is a full Next.js 13+ page.tsx file.
// Save as app/page.tsx and run `npm run dev`.

const navItems = [
  { label: "Home", href: "#home" },
  { label: "Services", href: "#services" },
  { label: "Gallery", href: "#gallery" },
  { label: "Reviews", href: "#reviews" },
  { label: "About", href: "#about" },
  { label: "FAQ", href: "#faq" },
  { label: "Contact", href: "#contact" },
];

const services = [
  { icon: <Sparkles className="w-6 h-6" />, title: "Tile & Grout Cleaning", desc: "Deep-clean extraction that lifts grime, soap scum, and years of stains." },
  { icon: <Droplets className="w-6 h-6" />, title: "Grout Sealing", desc: "Premium penetrating sealers to repel moisture and reduce re-staining." },
  { icon: <Hammer className="w-6 h-6" />, title: "Regrouting & Recaulking", desc: "Replace failing grout/caulk to stop leaks and restore a crisp, clean look." },
  { icon: <Ruler className="w-6 h-6" />, title: "Grout Color Sealing", desc: "Even out discoloration and lock in a like-new, uniform grout color." },
  { icon: <ShieldCheck className="w-6 h-6" />, title: "Shower Restoration", desc: "From mildew to minerals—revive tile showers with lasting protection." },
  { icon: <Sparkles className="w-6 h-6" />, title: "Stone Polishing (Optional)", desc: "Polish and hone natural stone for a refined, low-sheen finish." },
];

const gallery = [
  "https://images.unsplash.com/photo-1600566752707-8d2d3d48fb24?q=80&w=1600&auto=format&fit=crop",
  "https://images.unsplash.com/photo-1616594039964-ae9021a968df?q=80&w=1600&auto=format&fit=crop",
  "https://images.unsplash.com/photo-1600566753151-384129cb4bd8?q=80&w=1600&auto=format&fit=crop",
  "https://images.unsplash.com/photo-1582582429416-d6d6c2dff4e4?q=80&w=1600&auto=format&fit=crop",
  "https://images.unsplash.com/photo-1582582429416-789c8792ad7b?q=80&w=1600&auto=format&fit=crop",
  "https://images.unsplash.com/photo-1579888388782-32d66c1613e4?q=80&w=1600&auto=format&fit=crop",
];

const reviews = [
  { name: "Alex P.", text: "Our shower looks brand new. Fast, friendly, and meticulous!", rating: 5 },
  { name: "Jamie R.", text: "The color-seal matched perfectly. Huge difference—highly recommend.", rating: 5 },
  { name: "Morgan T.", text: "They revived our kitchen floor in an afternoon. Worth every penny.", rating: 5 },
];

const faqs = [
  { q: "How long does grout color sealing last?", a: "With proper care and neutral cleaners, color sealing typically lasts 5–10 years." },
  { q: "Do you offer free estimates?", a: "Yes—virtual or on-site quotes are free with no obligation." },
  { q: "How soon can we use the shower/floors?", a: "Floors are walkable within hours; showers usually need 24 hours before use." },
  { q: "Are your products safe for kids and pets?", a: "We use pro-grade, low-VOC products and ensure proper ventilation." },
];

const phoneNumber = "+1 (555) 123-4567"; // TODO: replace with your real number
const emailAddress = "hello@groutrestorations.com"; // TODO: replace with your real email
const serviceArea = "Greater Metro Area"; // TODO: replace

function StarRow({ count = 5 }: { count?: number }) {
  return (
    <div className="flex items-center gap-1" aria-label={`${count} star rating`}>
      {Array.from({ length: count }).map((_, i) => (
        <Star key={i} className="w-4 h-4 fill-current" />
      ))}
    </div>
  );
}

const Section = ({ id, children, className = "" }: { id?: string; children: React.ReactNode; className?: string }) => (
  <section id={id} className={`scroll-mt-24 ${className}`}>{children}</section>
);

// 🔹 Header
function Header() {
  return (
    <header className="fixed top-0 left-0 w-full bg-white shadow z-50">
      <div className="max-w-6xl mx-auto px-4 py-3 flex items-center justify-between">
        <a href="#home" className="font-bold text-xl">Grout Restorations</a>
        <nav className="hidden md:flex gap-6">
          {navItems.map((item) => (
            <a key={item.href} href={item.href} className="hover:text-blue-600">
              {item.label}
            </a>
          ))}
        </nav>
        <a href={`tel:${phoneNumber}`} className="flex items-center gap-2 bg-blue-600 text-white px-4 py-2 rounded-2xl shadow">
          <Phone className="w-4 h-4" /> {phoneNumber}
        </a>
      </div>
    </header>
  );
}

// 🔹 Hero
function Hero() {
  return (
    <Section id="home" className="pt-32 pb-20 bg-gradient-to-r from-blue-50 to-white">
      <div className="max-w-5xl mx-auto text-center">
        <motion.h1 initial={{ opacity: 0, y: 20 }} animate={{ opacity: 1, y: 0 }} className="text-4xl md:text-6xl font-bold mb-6">
          Revive Your Tile & Grout
        </motion.h1>
        <p className="text-lg md:text-xl mb-8">Professional cleaning, sealing, and restoration that makes surfaces look new again.</p>
        <a href="#contact" className="inline-flex items-center gap-2 bg-blue-600 text-white px-6 py-3 rounded-2xl shadow text-lg">
          <Calendar className="w-5 h-5" /> Request a Free Quote
        </a>
      </div>
    </Section>
  );
}

// 🔹 ValueBar
function ValueBar() {
  return (
    <div className="bg-blue-600 text-white py-6">
      <div className="max-w-6xl mx-auto flex flex-col md:flex-row justify-around gap-4 text-center">
        <div className="flex items-center gap-2 justify-center"><ShieldCheck className="w-5 h-5" /> Licensed & Insured</div>
        <div className="flex items-center gap-2 justify-center"><CheckCircle2 className="w-5 h-5" /> Satisfaction Guaranteed</div>
        <div className="flex items-center gap-2 justify-center"><Clock className="w-5 h-5" /> Flexible Scheduling</div>
      </div>
    </div>
  );
}

// 🔹 Services
function Services() {
  return (
    <Section id="services" className="py-20 bg-gray-50">
      <div className="max-w-6xl mx-auto px-4">
        <h2 className="text-3xl font-bold text-center mb-12">Our Services</h2>
        <div className="grid md:grid-cols-3 gap-8">
          {services.map((s, i) => (
            <motion.div key={i} initial={{ opacity: 0, y: 20 }} whileInView={{ opacity: 1, y: 0 }} viewport={{ once: true }} className="bg-white rounded-2xl shadow p-6">
              <div className="text-blue-600 mb-4">{s.icon}</div>
              <h3 className="font-semibold text-lg mb-2">{s.title}</h3>
              <p className="text-gray-600">{s.desc}</p>
            </motion.div>
          ))}
        </div>
      </div>
    </Section>
  );
}

// 🔹 Gallery
function Gallery() {
  return (
    <Section id="gallery" className="py-20">
      <div className="max-w-6xl mx-auto px-4">
        <h2 className="text-3xl font-bold text-center mb-12">Before & After Gallery</h2>
        <div className="grid grid-cols-2 md:grid-cols-3 gap-4">
          {gallery.map((src, i) => (
            <img key={i} src={src} alt="Grout restoration work" className="rounded-2xl shadow" />
          ))}
        </div>
      </div>
    </Section>
  );
}

// 🔹 Reviews
function Reviews() {
  return (
    <Section id="reviews" className="py-20 bg-gray-50">
      <div className="max-w-6xl mx-auto px-4">
        <h2 className="text-3xl font-bold text-center mb-12">Customer Reviews</h2>
        <div className="grid md:grid-cols-3 gap-8">
          {reviews.map((r, i) => (
            <div key={i} className="bg-white rounded-2xl shadow p-6 flex flex-col">
              <StarRow />
              <Quote className="w-6 h-6 text-blue-600 my-4" />
              <p className="text-gray-700 mb-4 flex-grow">“{r.text}”</p>
              <p className="font-semibold">— {r.name}</p>
            </div>
          ))}
        </div>
      </div>
    </Section>
  );
}

// 🔹 About
function About() {
  return (
    <Section id="about" className="py-20">
      <div className="max-w-4xl mx-auto px-4 text-center">
        <h2 className="text-3xl font-bold mb-6">About Us</h2>
        <p className="text-gray-700 leading-relaxed">
          At Grout Restorations, we specialize in bringing tired tile and grout back to life. With years of experience, premium products, and attention to detail, our goal is simple: beautiful, healthy surfaces you’ll love to use every day.
        </p>
      </div>
    </Section>
  );
}

// 🔹 FAQ
function FAQ() {
  return (
    <Section id="faq" className="py-20 bg-gray-50">
      <div className="max-w-3xl mx-auto px-4">
        <h2 className="text-3xl font-bold text-center mb-12">Frequently Asked Questions</h2>
        <div className="space-y-6">
          {faqs.map((f, i) => (
            <div key={i} className="bg-white rounded-2xl shadow p-6">
              <h3 className="font-semibold mb-2">{f.q}</h3>
              <p className="text-gray-600">{f.a}</p>
            </div>
          ))}
        </div>
      </div>
    </Section>
  );
}

// 🔹 Contact
function Contact() {
  return (
    <Section id="contact" className="py-20">
      <div className="max-w-5xl mx-auto px-4 grid md:grid-cols-2 gap-12 items-center">
        <div>
          <h2 className="text-3xl font-bold mb-6">Get in Touch</h2>
          <p className="text-gray-700 mb-6">Serving the {serviceArea}. Contact us today for a free consultation.</p>
          <ul className="space-y-4">
            <li className="flex items-center gap-2"><Phone className="w-5 h-5 text-blue-600" /> <a href={`tel:${phoneNumber}`}>{phoneNumber}</a></li>
            <li className="flex items-center gap-2"><Mail className="w-5 h-5 text-blue-600" /> <a href={`mailto:${emailAddress}`}>{emailAddress}</a></li>
            <li className="flex items-center gap-2"><MapPin className="w-5 h-5 text-blue-600" /> {serviceArea}</li>
          </ul>
        </div>
        <form className="bg-gray-50 p-6 rounded-2xl shadow space-y-4">
          <input type="text" placeholder="Your Name" className="w-full border rounded-xl px-4 py-2" />
          <input type="email" placeholder="Your Email" className="w-full border rounded-xl px-4 py-2" />
          <textarea placeholder="Your Message" className="w-full border rounded-xl px-4 py-2 h-32"></textarea>
          <button type="submit" className="bg-blue-600 text-white px-6 py-2 rounded-2xl shadow">Send Message</button>
        </form>
      </div>
    </Section>
  );
}

// 🔹 CTA
function CTA() {
  return (
    <div className="bg-blue-600 text-white py-12 text-center">
      <h2 className="text-2xl font-bold mb-4">Ready to restore your grout?</h2>
      <a href="#contact" className="bg-white text-blue-600 px-6 py-3 rounded-2xl shadow text-lg font-semibold">Get a Free Quote</a>
    </div>
  );
}

// 🔹 Footer
function Footer() {
  return (
    <footer className="bg-gray-900 text-gray-400 py-10 mt-20">
      <div className="max-w-6xl mx-auto px-4 grid md:grid-cols-3 gap-8">
        <div>
          <h3 className="text-white font-bold mb-3">Grout Restorations</h3>
          <p>Tile & Grout Cleaning • Sealing • Restoration</p>
        </div>
        <div>
          <h3 className="text-white font-bold mb-3">Quick Links</h3>
          <ul className="space-y-2">
            {navItems.map((item) => (
              <li key={item.href}><a href={item.href} className="hover:text-white">{item.label}</a></li>
            ))}
          </ul>
        </div>
        <div>
          <h3 className="text-white font-bold mb-3">Connect</h3>
          <div className="flex gap-4">
            <a href="#" aria-label="Facebook"><Facebook className="w-5 h-5" /></a>
            <a href="#" aria-label="Instagram"><Instagram className="w-5 h-5" /></a>
          </div>
        </div>
      </div>
      <p className="text-center text-gray-500 mt-10">© {new Date().getFullYear()} Grout Restorations. All rights reserved.</p>
    </footer>
  );
}

export default function Page() {
  React.useEffect(() => {
    document.title = "Grout Restorations | Tile & Grout Cleaning, Sealing, and Restoration";
    const metaDesc = document.querySelector('meta[name="description"]') || document.createElement('meta');
    metaDesc.setAttribute('name', 'description');
    metaDesc.setAttribute('content', 'Professional tile and grout cleaning, color sealing, regrouting, and shower restoration. Free quotes. Licensed & insured.');
    document.head.appendChild(metaDesc);
  }, []);

  return (
    <main className="font-sans text-gray-900">
      <Header />
      <Hero />
      <ValueBar />
      <Services />
      <Gallery />
      <Reviews />
      <About />
      <FAQ />
      <Contact />
      <CTA />
      <Footer />
    </main>
  );
}
