import { Button } from "@/components/ui/button";
import { Card, CardContent } from "@/components/ui/card";
import { motion } from "framer-motion";

export default function LandingPage() {
  return (
    <div className="min-h-screen bg-[#0F1115] text-white px-6 py-10">
      {/* Hero */}
      <section className="text-center space-y-6">
        <motion.h1 
          initial={{ opacity: 0, y: -30 }} 
          animate={{ opacity: 1, y: 0 }} 
          transition={{ duration: 0.8 }}
          className="text-4xl md:text-6xl font-bold"
        >
          Мадейра — в твоем кармане
        </motion.h1>
        <p className="text-lg text-gray-400 max-w-xl mx-auto">
          Умный путеводитель с картой, бронированиями, переводчиком и персональным гидом
        </p>
        <div className="flex justify-center gap-4">
          <Button className="bg-[#00C2FF] text-black text-lg">Скачать</Button>
          <Button variant="outline" className="text-white border-white">Смотреть демо</Button>
        </div>
      </section>

      {/* Features */}
      <section className="mt-20 grid md:grid-cols-3 gap-6">
        {[
          { title: "Интерактивная карта", desc: "Тропы, пляжи, виды — всё на одной карте." },
          { title: "Онлайн-бронирование", desc: "Жильё, транспорт, экскурсии — мгновенно." },
          { title: "Переводчик и гид", desc: "Общайся с местными и открывай больше." },
        ].map((f, i) => (
          <Card key={i} className="bg-[#1A1D22] border-none">
            <CardContent className="p-6">
              <h3 className="text-xl font-semibold mb-2">{f.title}</h3>
              <p className="text-gray-400">{f.desc}</p>
            </CardContent>
          </Card>
        ))}
      </section>

      {/* Screenshots (мокапы позже можно анимировать) */}
      <section className="mt-24 text-center">
        <h2 className="text-3xl font-bold mb-6">Как выглядит приложение</h2>
        <div className="flex flex-wrap justify-center gap-4">
          <img src="/mockup1.png" alt="Экран 1" className="w-64 rounded-2xl shadow-xl" />
          <img src="/mockup2.png" alt="Экран 2" className="w-64 rounded-2xl shadow-xl" />
        </div>
      </section>

      {/* CTA */}
      <section className="mt-24 bg-[#1A1D22] p-8 rounded-2xl text-center">
        <h3 className="text-2xl font-bold mb-4">Будь первым, кто попробует</h3>
        <p className="text-gray-400 mb-6">Подпишись на Telegram или оставь email</p>
        <div className="flex flex-col md:flex-row justify-center gap-4">
          <input 
            type="email" 
            placeholder="Твой email..." 
            className="px-4 py-2 rounded-lg bg-[#0F1115] border border-gray-600 text-white"
          />
          <Button className="bg-[#FF5A36] text-white">Подписаться</Button>
        </div>
      </section>

      {/* Footer */}
      <footer className="mt-20 text-center text-sm text-gray-500">
        © 2025 Madeira Guide. Все права защищены.
      </footer>
    </div>
  );
}
