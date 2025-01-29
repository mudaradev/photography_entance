# photography_entance
import "./globals.css"
import { Montserrat, Open_Sans } from "next/font/google"
import Link from "next/link"

const montserrat = Montserrat({ subsets: ["latin"], variable: "--font-montserrat" })
const openSans = Open_Sans({ subsets: ["latin"], variable: "--font-open-sans" })

export const metadata = {
  title: "Photography Masterclass",
  description: "Transform your photography skills in 4 weeks",
}

export default function RootLayout({
  children,
}: {
  children: React.ReactNode
}) {
  return (
    <html lang="en" className={`${montserrat.variable} ${openSans.variable}`}>
      <body className="font-sans bg-white text-navy-900">
        <header className="bg-navy-900 text-white py-4">
          <div className="container mx-auto px-4 flex justify-between items-center">
            <Link href="/" className="text-2xl font-bold font-montserrat">
              PhotoMaster
            </Link>
            <nav>
              <ul className="flex space-x-6">
                <li>
                  <Link href="#course-details" className="hover:text-yellow-400 transition-colors">
                    Course Details
                  </Link>
                </li>
                <li>
                  <Link href="#testimonials" className="hover:text-yellow-400 transition-colors">
                    Testimonials
                  </Link>
                </li>
                <li>
                  <Link href="#enroll" className="hover:text-yellow-400 transition-colors">
                    Enroll Now
                  </Link>
                </li>
              </ul>
            </nav>
          </div>
        </header>
        <main>{children}</main>
        <footer className="bg-navy-900 text-white py-8 mt-16">
          <div className="container mx-auto px-4 text-center">
            <p>&copy; 2023 PhotoMaster. All rights reserved.</p>
          </div>
        </footer>
      </body>
    </html>
  )
}

