{
  "name": "clinixsphere-site",
  "version": "1.0.0",
  "private": true,
  "scripts": {
    "dev": "next dev",
    "build": "next build",
    "start": "next start",
    "lint": "next lint"
  },
  "dependencies": {
    "next": "latest",
    "react": "latest",
    "react-dom": "latest",
    "tailwindcss": "latest",
    "postcss": "latest",
    "autoprefixer": "latest"
  }
}
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: [
    "./pages/**/*.{js,ts,jsx,tsx}",
    "./components/**/*.{js,ts,jsx,tsx}",
  ],
  theme: {
    extend: {},
  },
  plugins: [],
}
module.exports = {
  plugins: {
    tailwindcss: {},
    autoprefixer: {},
  },
}
@tailwind base;
@tailwind components;
@tailwind utilities;

/* Custom Global Styles */
body {
  @apply bg-white text-gray-800 font-sans;
}
import '../styles/globals.css'

function MyApp({ Component, pageProps }) {
  return <Component {...pageProps} />
}

export default MyApp
import { Html, Head, Main, NextScript } from 'next/document'

export default function Document() {
  return (
    <Html lang="en">
      <Head>
        <meta name="description" content="ClinixSphere — Comprehensive Clinical Research Software Suite" />
        <meta property="og:title" content="ClinixSphere" />
        <meta property="og:description" content="Simplifying Clinical Research. One Platform, Endless Possibilities." />
        <meta property="og:type" content="website" />
        <link rel="icon" href="/favicon.ico" />
      </Head>
      <body>
        <Main />
        <NextScript />
      </body>
    </Html>
  )
}
import Link from 'next/link'

export default function Header() {
  return (
    <header className="w-full py-4 px-6 bg-white shadow-md sticky top-0 z-50">
      <div className="flex justify-between items-center max-w-7xl mx-auto">
        <Link href="/">
          <span className="text-2xl font-bold text-blue-600 cursor-pointer">ClinixSphere</span>
        </Link>
        <nav className="space-x-6 text-gray-700 hidden md:flex">
          <Link href="/">Home</Link>
          <Link href="/products">Products</Link>
          <Link href="/about">About</Link>
          <Link href="/pricing">Pricing</Link>
          <Link href="/blog">Blog</Link>
          <Link href="/contact">Contact</Link>
          <Link href="/login" className="text-blue-600 font-semibold">Login</Link>
        </nav>
      </div>
    </header>
  )
}
import Link from 'next/link'

export default function Footer() {
  return (
    <footer className="bg-gray-100 text-gray-600 py-6 mt-10">
      <div className="max-w-7xl mx-auto px-6 flex flex-col md:flex-row justify-between">
        <div>
          <h3 className="text-xl font-bold mb-2">ClinixSphere</h3>
          <p>© {new Date().getFullYear()} ClinixSphere. All rights reserved.</p>
        </div>
        <div className="flex space-x-6 mt-4 md:mt-0">
          <Link href="/privacy">Privacy Policy</Link>
          <Link href="/terms">Terms of Service</Link>
        </div>
      </div>
    </footer>
  )
}
import Link from 'next/link'

export default function Hero() {
  return (
    <section className="bg-blue-50 text-center py-20 px-6">
      <div className="max-w-4xl mx-auto">
        <h1 className="text-4xl md:text-5xl font-extrabold text-gray-900 mb-6">
          Simplifying Clinical Research.<br/> One Platform, Endless Possibilities.
        </h1>
        <p className="text-lg text-gray-700 mb-8">
          Affordable. Intelligent. Ready for Your Next Breakthrough.
        </p>
        <div className="space-x-4">
          <Link href="/contact" className="inline-block bg-blue-600 text-white py-3 px-6 rounded-full hover:bg-blue-700 transition">
            Schedule Demo
          </Link>
          <Link href="/products" className="inline-block bg-gray-200 text-blue-600 py-3 px-6 rounded-full hover:bg-gray-300 transition">
            Learn More
          </Link>
        </div>
      </div>
    </section>
  )
}
import Head from 'next/head'
import Header from '../components/Header'
import Footer from '../components/Footer'
import Hero from '../components/Hero'

export default function Home() {
  return (
    <>
      <Head>
        <title>ClinixSphere | Simplifying Clinical Research</title>
        <meta name="description" content="Affordable, easy-to-use clinical research software: EDC, CTMS, and QMS systems in one platform." />
      </Head>
      
      <Header />
      <main>
        <Hero />
        
        {/* About Section */}
        <section className="py-16 px-6 bg-white">
          <div className="max-w-5xl mx-auto text-center">
            <h2 className="text-3xl font-bold mb-6 text-gray-900">All-in-One Clinical Research Software</h2>
            <p className="text-gray-700 text-lg">
              ClinixSphere provides affordable, user-friendly, and powerful tools
              to manage clinical trials from startup to closeout. Whether you’re a small team or a multi-site powerhouse, we’re built for you.
            </p>
          </div>
        </section>

        {/* Product Highlights Section */}
        <section className="py-16 bg-gray-50">
          <div className="max-w-6xl mx-auto grid grid-cols-1 md:grid-cols-3 gap-8 px-6">
            <div className="bg-white p-6 rounded-xl shadow-md text-center">
              <h3 className="text-2xl font-bold text-blue-600 mb-4">EDC System</h3>
              <p className="text-gray-700 mb-6">Capture clinical trial data quickly, securely, and accurately.</p>
              <a href="/products#edc" className="text-blue-600 font-semibold hover:underline">Learn More →</a>
            </div>
            <div className="bg-white p-6 rounded-xl shadow-md text-center">
              <h3 className="text-2xl font-bold text-blue-600 mb-4">CTMS Platform</h3>
              <p className="text-gray-700 mb-6">Manage trial milestones, budgets, and sites with ease.</p>
              <a href="/products#ctms" className="text-blue-600 font-semibold hover:underline">Learn More →</a>
            </div>
            <div className="bg-white p-6 rounded-xl shadow-md text-center">
              <h3 className="text-2xl font-bold text-blue-600 mb-4">QMS Manager</h3>
              <p className="text-gray-700 mb-6">Ensure compliance and streamline your quality management processes.</p>
              <a href="/products#qms" className="text-blue-600 font-semibold hover:underline">Learn More →</a>
            </div>
          </div>
        </section>

        {/* Secondary Call to Action */}
        <section className="py-16 px-6 text-center">
          <div className="max-w-4xl mx-auto">
            <h2 className="text-3xl font-bold text-gray-900 mb-6">Ready to streamline your research?</h2>
            <a href="/contact" className="inline-block bg-blue-600 text-white py-3 px-6 rounded-full hover:bg-blue-700 transition">
              Schedule Your Demo
            </a>
          </div>
        </section>
      </main>

      <Footer />
    </>
  )
}
import Head from 'next/head'
import Header from '../components/Header'
import Footer from '../components/Footer'

export default function Products() {
  return (
    <>
      <Head>
        <title>ClinixSphere Products | EDC, CTMS, QMS</title>
        <meta name="description" content="Explore ClinixSphere's suite: Electronic Data Capture (EDC), Clinical Trial Management System (CTMS), and Quality Management System (QMS)." />
      </Head>

      <Header />
      <main className="py-16 px-6 bg-gray-50">
        <section className="max-w-6xl mx-auto mb-16 text-center">
          <h1 className="text-4xl font-bold text-gray-900 mb-4">Our Products</h1>
          <p className="text-lg text-gray-700">
            ClinixSphere's suite gives you full control of your research — faster, simpler, and smarter.
          </p>
        </section>

        {/* EDC Section */}
        <section id="edc" className="bg-white p-10 rounded-2xl shadow-md mb-12">
          <h2 className="text-3xl font-bold text-blue-600 mb-4">Electronic Data Capture (EDC)</h2>
          <p className="text-gray-700 mb-6">
            Capture, validate, and monitor clinical trial data easily with our intuitive EDC system.
          </p>
          <ul className="list-disc list-inside text-gray-700 mb-6">
            <li>Easy form builders and edit checks</li>
            <li>Real-time data entry and remote monitoring</li>
            <li>Secure, compliant with 21 CFR Part 11</li>
          </ul>
          <a href="/contact" className="text-blue-600 font-semibold hover:underline">Schedule a Demo →</a>
        </section>

        {/* CTMS Section */}
        <section id="ctms" className="bg-white p-10 rounded-2xl shadow-md mb-12">
          <h2 className="text-3xl font-bold text-blue-600 mb-4">Clinical Trial Management System (CTMS)</h2>
          <p className="text-gray-700 mb-6">
            Track site performance, study budgets, trial timelines, and compliance in one platform.
          </p>
          <ul className="list-disc list-inside text-gray-700 mb-6">
            <li>Study milestones and alerts</li>
            <li>Investigator and site management</li>
            <li>Document management & audit trails</li>
          </ul>
          <a href="/contact" className="text-blue-600 font-semibold hover:underline">Book a Demo →</a>
        </section>

        {/* QMS Section */}
        <section id="qms" className="bg-white p-10 rounded-2xl shadow-md">
          <h2 className="text-3xl font-bold text-blue-600 mb-4">Quality Management System (QMS)</h2>
          <p className="text-gray-700 mb-6">
            Stay compliant and efficient with built-in quality management features.
          </p>
          <ul className="list-disc list-inside text-gray-700 mb-6">
            <li>CAPA management and tracking</li>
            <li>Training tracking for staff</li>
            <li>Inspection readiness modules</li>
          </ul>
          <a href="/contact" className="text-blue-600 font-semibold hover:underline">Request a Walkthrough →</a>
        </section>
      </main>

      <Footer />
    </>
  )
}
import Head from 'next/head'
import Header from '../components/Header'
import Footer from '../components/Footer'

export default function About() {
  return (
    <>
      <Head>
        <title>About ClinixSphere | Our Mission and Vision</title>
        <meta name="description" content="Learn more about ClinixSphere — dedicated to making clinical research easier, faster, and more affordable." />
      </Head>

      <Header />
      <main className="py-16 px-6 bg-white">
        <section className="max-w-5xl mx-auto text-center mb-16">
          <h1 className="text-4xl font-bold text-gray-900 mb-6">About ClinixSphere</h1>
          <p className="text-lg text-gray-700">
            Our mission is simple: to simplify clinical research for organizations of all sizes.
            By offering a unified platform for EDC, CTMS, and QMS needs, we empower teams to focus on
            what matters — advancing healthcare breakthroughs.
          </p>
        </section>

        {/* Story Section */}
        <section className="max-w-6xl mx-auto grid md:grid-cols-2 gap-12 mb-16">
          <div>
            <h2 className="text-3xl font-bold text-blue-600 mb-4">Our Story</h2>
            <p className="text-gray-700 mb-6">
              ClinixSphere was founded by clinical researchers and technology innovators who were frustrated
              with complex, overpriced trial management tools. We imagined a better way — building intuitive,
              affordable software that scales with your team.
            </p>
            <p className="text-gray-700">
              From startups to established CROs, ClinixSphere is designed to fit seamlessly into your research workflows
              without overwhelming your staff.
            </p>
          </div>

          <div className="flex items-center justify-center">
            <img src="/images/about-placeholder.png" alt="ClinixSphere Team" className="rounded-xl shadow-md" />
          </div>
        </section>

        {/* Values Section */}
        <section className="bg-gray-50 py-16 px-6 rounded-2xl shadow-inner text-center">
          <h2 className="text-3xl font-bold text-gray-900 mb-8">Our Core Values</h2>
          <div className="grid md:grid-cols-3 gap-8">
            <div>
              <h3 className="text-xl font-semibold text-blue-600 mb-2">Trust</h3>
              <p className="text-gray-700">Transparent pricing and processes you can rely on.</p>
            </div>
            <div>
              <h3 className="text-xl font-semibold text-blue-600 mb-2">Innovation</h3>
              <p className="text-gray-700">Leveraging technology to keep you ahead of the curve.</p>
            </div>
            <div>
              <h3 className="text-xl font-semibold text-blue-600 mb-2">Support</h3>
              <p className="text-gray-700">Friendly, expert help whenever you need it.</p>
            </div>
          </div>
        </section>
      </main>

      <Footer />
    </>
  )
}
import Head from 'next/head'
import Header from '../components/Header'
import Footer from '../components/Footer'

export default function Pricing() {
  return (
    <>
      <Head>
        <title>ClinixSphere Pricing | Simple, Transparent Plans</title>
        <meta name="description" content="Explore ClinixSphere pricing plans — affordable, flexible options for clinical research teams of all sizes." />
      </Head>

      <Header />
      <main className="py-16 px-6 bg-gray-50">
        <section className="max-w-6xl mx-auto text-center mb-16">
          <h1 className="text-4xl font-bold text-gray-900 mb-4">Simple, Transparent Pricing</h1>
          <p className="text-lg text-gray-700">
            No hidden fees. Just powerful clinical trial management tools — scaled to your needs.
          </p>
        </section>

        {/* Pricing Cards */}
        <section className="grid md:grid-cols-3 gap-8 max-w-6xl mx-auto mb-16">
          {/* Starter Plan */}
          <div className="bg-white p-8 rounded-2xl shadow-md text-center">
            <h2 className="text-2xl font-bold text-blue-600 mb-4">Starter</h2>
            <p className="text-4xl font-bold text-gray-900 mb-6">$199<span className="text-lg text-gray-600">/month</span></p>
            <ul className="text-gray-700 mb-8 space-y-3">
              <li>Up to 3 active studies</li>
              <li>EDC & CTMS modules</li>
              <li>Email support</li>
            </ul>
            <a href="/contact" className="inline-block bg-blue-600 text-white py-3 px-6 rounded-full hover:bg-blue-700 transition">
              Get Started
            </a>
          </div>

          {/* Professional Plan */}
          <div className="bg-white p-8 rounded-2xl shadow-md text-center border-2 border-blue-600">
            <h2 className="text-2xl font-bold text-blue-600 mb-4">Professional</h2>
            <p className="text-4xl font-bold text-gray-900 mb-6">$499<span className="text-lg text-gray-600">/month</span></p>
            <ul className="text-gray-700 mb-8 space-y-3">
              <li>Unlimited studies</li>
              <li>Full EDC, CTMS, and QMS suite</li>
              <li>Priority support</li>
              <li>Basic AI Insights</li>
            </ul>
            <a href="/contact" className="inline-block bg-blue-600 text-white py-3 px-6 rounded-full hover:bg-blue-700 transition">
              Start Today
            </a>
          </div>

          {/* Enterprise Plan */}
          <div className="bg-white p-8 rounded-2xl shadow-md text-center">
            <h2 className="text-2xl font-bold text-blue-600 mb-4">Enterprise</h2>
            <p className="text-2xl font-bold text-gray-900 mb-6">Custom Quote</p>
            <ul className="text-gray-700 mb-8 space-y-3">
              <li>Multi-site and global trials</li>
              <li>Custom integrations</li>
              <li>Dedicated account manager</li>
              <li>Advanced AI features (coming soon)</li>
            </ul>
            <a href="/contact" className="inline-block bg-blue-600 text-white py-3 px-6 rounded-full hover:bg-blue-700 transition">
              Request a Quote
            </a>
          </div>
        </section>

        {/* Final CTA */}
        <section className="text-center">
          <h2 className="text-2xl font-bold text-gray-900 mb-6">Not sure which plan fits?</h2>
          <a href="/contact" className="inline-block bg-blue-600 text-white py-3 px-6 rounded-full hover:bg-blue-700 transition">
            Contact Our Team
          </a>
        </section>
      </main>

      <Footer />
    </>
  )
}
import { useState } from 'react'

export default function ContactForm() {
  const [formData, setFormData] = useState({ name: '', email: '', message: '' })
  const [status, setStatus] = useState('')

  const handleChange = (e) => {
    setFormData({ ...formData, [e.target.name]: e.target.value })
  }

  const handleSubmit = async (e) => {
    e.preventDefault()
    setStatus('Sending...')

    const res = await fetch('/api/contact', {
      method: 'POST',
      headers: { 'Content-Type': 'application/json' },
      body: JSON.stringify(formData),
    })

    if (res.ok) {
      setStatus('Message sent! ✅')
      setFormData({ name: '', email: '', message: '' })
    } else {
      setStatus('Something went wrong ❌')
    }
  }

  return (
    <form onSubmit={handleSubmit} className="space-y-6 max-w-2xl mx-auto">
      <input
        type="text"
        name="name"
        placeholder="Your Name"
        value={formData.name}
        onChange={handleChange}
        required
        className="w-full p-3 border rounded-lg"
      />
      <input
        type="email"
        name="email"
        placeholder="Your Email"
        value={formData.email}
        onChange={handleChange}
        required
        className="w-full p-3 border rounded-lg"
      />
      <textarea
        name="message"
        placeholder="Your Message"
        value={formData.message}
        onChange={handleChange}
        required
        rows="5"
        className="w-full p-3 border rounded-lg"
      ></textarea>
      <button type="submit" className="bg-blue-600 text-white py-3 px-6 rounded-full hover:bg-blue-700 transition">
        Send Message
      </button>
      {status && <p className="text-center mt-4">{status}</p>}
    </form>
  )
}
export default async function handler(req, res) {
  if (req.method === 'POST') {
    const { name, email, message } = req.body

    // For now, just simulate success
    console.log('Contact form submitted:', { name, email, message })

    res.status(200).json({ message: 'Success' })
  } else {
    res.status(405).json({ message: 'Method Not Allowed' })
  }
}
import Head from 'next/head'
import Header from '../components/Header'
import Footer from '../components/Footer'
import ContactForm from '../components/ContactForm'

export default function Contact() {
  return (
    <>
      <Head>
        <title>Contact ClinixSphere | Get in Touch</title>
        <meta name="description" content="Contact ClinixSphere today to learn more about how our clinical research software can help your team succeed." />
      </Head>

      <Header />
      <main className="py-16 px-6 bg-white">
        <section className="max-w-5xl mx-auto text-center mb-12">
          <h1 className="text-4xl font-bold text-gray-900 mb-4">Contact Us</h1>
          <p className="text-lg text-gray-700">
            Have questions or want a live demo? Fill out the form below or schedule a time with our team.
          </p>
        </section>

        <ContactForm />

        {/* Calendly Embed Placeholder */}
        <section className="py-16 text-center">
          <h2 className="text-2xl font-bold text-gray-900 mb-4">Prefer to book a time?</h2>
          <p className="text-gray-700 mb-8">Schedule your live demo directly on our calendar:</p>
          <div className="max-w-4xl mx-auto">
            <iframe
              src="https://calendly.com/YOUR-CALENDLY-URL"
              width="100%"
              height="600"
              frameBorder="0"
              className="rounded-xl shadow-md"
              allowFullScreen
            ></iframe>
          </div>
        </section>
      </main>

      <Footer />
    </>
  )
}
import Link from 'next/link'

export default function BlogPostCard({ title, excerpt, link }) {
  return (
    <div className="bg-white p-6 rounded-xl shadow-md hover:shadow-lg transition">
      <h3 className="text-2xl font-bold text-blue-600 mb-4">{title}</h3>
      <p className="text-gray-700 mb-6">{excerpt}</p>
      <Link href={link} className="text-blue-600 font-semibold hover:underline">
        Read More →
      </Link>
    </div>
  )
}
import Head from 'next/head'
import Header from '../components/Header'
import Footer from '../components/Footer'
import BlogPostCard from '../components/BlogPostCard'

export default function Blog() {
  const posts = [
    {
      title: '5 Ways Technology is Transforming Clinical Trials',
      excerpt: 'Explore how modern platforms like ClinixSphere are streamlining trial management, improving data quality, and reducing costs...',
      link: '/blog/technology-transforming-trials'
    },
    {
      title: 'Understanding EDC, CTMS, and QMS: A Beginner’s Guide',
      excerpt: 'New to clinical trial software? Here’s a simple breakdown of what EDC, CTMS, and QMS systems are — and why they matter...',
      link: '/blog/understanding-edc-ctms-qms'
    },
    {
      title: 'How to Choose the Right Clinical Trial Management Software',
      excerpt: 'Evaluating new systems? Discover the key features you should prioritize when selecting a clinical research suite...',
      link: '/blog/choosing-clinical-trial-software'
    }
  ]

  return (
    <>
      <Head>
        <title>ClinixSphere Blog | Clinical Research Insights</title>
        <meta name="description" content="ClinixSphere Blog — stay updated with tips, insights, and news in the world of clinical research and trial management technology." />
      </Head>

      <Header />
      <main className="py-16 px-6 bg-gray-50">
        <section className="max-w-6xl mx-auto text-center mb-16">
          <h1 className="text-4xl font-bold text-gray-900 mb-4">ClinixSphere Blog</h1>
          <p className="text-lg text-gray-700">
            Insights, updates, and best practices for modern clinical research.
          </p>
        </section>

        <section className="grid md:grid-cols-3 gap-8 max-w-6xl mx-auto">
          {posts.map((post, idx) => (
            <BlogPostCard 
              key={idx}
              title={post.title}
              excerpt={post.excerpt}
              link={post.link}
            />
          ))}
        </section>
      </main>

      <Footer />
    </>
  )
}
npx vercel
