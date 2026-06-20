import React from "react";

const HERO_IMAGE = "https://media.base44.com/images/public/6a35e6467d8d44e0af3a2fa5/94a327578_generated_image.png";

const badges = [
  { icon: "⏱", label: "15-Min Video Visit" },
  { icon: "🦷", label: "Licensed Dentist" },
  { icon: "💊", label: "Prescriptions When Appropriate" },
  { icon: "🏠", label: "No Office Visit Needed" },
];

export default function HeroSection({ bookingUrl }) {
  return (
    <section className="pt-16 min-h-screen bg-white relative overflow-hidden">
      <div className="max-w-6xl mx-auto px-6 h-full flex items-center">
        <div className="grid grid-cols-1 lg:grid-cols-2 gap-12 items-center py-20 w-full">
          {/* Left */}
          <div className="space-y-8">
            {/* Live status pill */}
            <div className="inline-flex items-center gap-2 bg-[#E8F5FC] text-[#4DB8E8] px-4 py-2 rounded-full text-sm font-semibold">
              <span className="relative flex h-2 w-2">
                <span className="animate-ping absolute inline-flex h-full w-full rounded-full bg-[#4DB8E8] opacity-75"></span>
                <span className="relative inline-flex rounded-full h-2 w-2 bg-[#4DB8E8]"></span>
              </span>
              Dentists Online Now
            </div>

            <h1 className="text-5xl lg:text-6xl font-bold text-[#121D2F] leading-tight font-heading">
              Talk to a Dentist{" "}
              <span className="text-[#4DB8E8]">Today</span>—{" "}
              <br className="hidden lg:block" />
              From{" "}
              <span className="text-[#4DB8E8]">Home</span>
            </h1>

            <p className="text-lg text-[#4A5568] leading-relaxed max-w-lg">
              Get fast relief for tooth pain, swelling, or infection with a licensed dentist in minutes. No waiting rooms, no office visits required.
            </p>

            {/* Badges */}
            <div className="flex flex-wrap gap-3">
              {badges.map((b) => (
                <div
                  key={b.label}
                  className="flex items-center gap-2 bg-[#F2F5F7] border border-[#E2E8F0] px-4 py-2 rounded-full text-sm font-medium text-[#121D2F]"
                >
                  <span>{b.icon}</span>
                  <span>{b.label}</span>
                </div>
              ))}
            </div>

            {/* CTA */}
            <div className="flex flex-col sm:flex-row items-start sm:items-center gap-4">
              <a
                href={bookingUrl}
                target="_blank"
                rel="noopener noreferrer"
                className="bg-[#4DB8E8] text-white px-8 py-4 rounded-full text-lg font-bold hover:bg-[#3AA8D8] transition-all hover:scale-105 shadow-lg shadow-[#4DB8E8]/25 min-h-[56px] flex items-center focus:outline focus:outline-2 focus:outline-[#4DB8E8] focus:outline-offset-2"
              >
                Talk to a Dentist Now →
              </a>
              <p className="text-xs text-[#718096]">Secure · HIPAA-Compliant · Available Online</p>
            </div>
          </div>

          {/* Right — image */}
          <div className="relative hidden lg:block">
            <div className="absolute inset-0 bg-gradient-to-br from-[#4DB8E8]/10 to-transparent rounded-3xl transform scale-105"></div>
            <img
              src={HERO_IMAGE}
              alt="Licensed dentist smiling in a modern dental office"
              className="relative z-10 w-full h-[560px] object-cover rounded-3xl shadow-2xl"
            />
            {/* Floating card */}
            <div className="absolute bottom-6 left-6 z-20 bg-white rounded-2xl p-4 shadow-xl border border-[#E2E8F0]">
              <div className="flex items-center gap-3">
                <div className="w-10 h-10 bg-[#E8F5FC] rounded-full flex items-center justify-center text-lg">✅</div>
                <div>
                  <p className="text-xs text-[#718096]">Next Available</p>
                  <p className="text-sm font-bold text-[#121D2F]">Today, within minutes</p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
  );
}
