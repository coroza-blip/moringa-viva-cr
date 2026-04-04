import Image from "next/image";
import Link from "next/link";

const products = [
  {
    name: "Calma Verde",
    price: "₡4,500",
    description:
      "Jabón artesanal con moringa, ideal para piel sensible. Su fórmula suave permite el uso diario, brindando limpieza y bienestar sin resecar la piel.",
    tags: ["Piel sensible", "Uso diario", "Limpieza suave"],
    image: "/calma-pack.jpg",
    alt: "Jabón Calma Verde con su empaque",
  },
  {
    name: "Vital Skin",
    price: "₡4,500",
    description:
      "Jabón hidratante de uso diario que ayuda a mantener la piel saludable, fresca y en equilibrio, aportando suavidad y cuidado natural.",
    tags: ["Hidratante", "Uso diario", "Suavidad"],
    image: "/vital-pack.jpg",
    alt: "Jabón Vital Skin con su empaque",
  },
  {
    name: "Moringa Detox",
    price: "₡4,500",
    description:
      "Jabón de limpieza profunda que elimina impurezas sin perder suavidad, ideal para mantener la piel limpia, fresca y equilibrada.",
    tags: ["Limpieza profunda", "Suavidad", "Piel equilibrada"],
    image: "/detox-pack.jpg",
    alt: "Jabón Moringa Detox con su empaque",
  },
];

function WhatsAppButton({
  text = "Consultar",
}: {
  text?: string;
}) {
  const whatsappLink =
    "https://wa.me/50672647175?text=Hola,%20quiero%20informaci%C3%B3n%20sobre%20los%20jabones%20de%20Moringa%20Viva%20CR";
  return (
    <Link
      href={whatsappLink}
      target="_blank"
      className="inline-flex items-center justify-center rounded-full bg-green-700 px-5 py-3 text-sm font-semibold text-white shadow-sm transition hover:bg-green-800"
    >
      {text}
    </Link>
  );
}

export default function Page() {
  return (
    <main className="min-h-screen bg-[#f8f5ef] text-[#1f2a1f]">
      {/* NAVBAR */}
      <header className="sticky top-0 z-50 border-b border-[#d9d2c6] bg-[#f8f5ef]/95 backdrop-blur">
        <div className="mx-auto flex max-w-7xl items-center justify-between px-6 py-4">
          <Link href="#" className="text-lg font-semibold tracking-wide">
            Moringa Viva CR
          </Link>

          <nav className="hidden gap-6 md:flex text-sm">
            <a href="#productos" className="hover:text-green-700">
              Productos
            </a>
            <a href="#nosotros" className="hover:text-green-700">
              Nosotros
            </a>
            <a href="#contacto" className="hover:text-green-700">
              Contacto
            </a>
          </nav>

          <Link
            href="https://wa.me/50672647175"
            target="_blank"
            className="rounded-full border border-green-700 px-4 py-2 text-sm font-medium text-green-700 transition hover:bg-green-700 hover:text-white"
          >
            WhatsApp
          </Link>
        </div>
      </header>

      {/* HERO */}
      <section className="mx-auto grid max-w-7xl gap-10 px-6 py-12 md:grid-cols-2 md:items-center md:py-20">
        <div>
          <p className="mb-3 text-sm uppercase tracking-[0.25em] text-green-700">
            Moringa Viva Costa Rica
          </p>
          <h1 className="max-w-xl text-4xl font-semibold leading-tight md:text-6xl">
            Naturaleza que se siente en tu piel
          </h1>
          <p className="mt-6 max-w-lg text-base leading-7 text-[#4b5a4b] md:text-lg">
            Elaborado con moringa natural para el cuidado diario de tu piel.
          </p>

          <div className="mt-8 flex flex-wrap gap-4">
            <WhatsAppButton text="WhatsApp" />
            <Link
              href="https://instagram.com/moringavivacr"
              target="_blank"
              className="inline-flex items-center justify-center rounded-full border border-[#bcc8b3] px-5 py-3 text-sm font-semibold text-[#2f3a2f] transition hover:bg-white"
            >
              @moringavivacr
            </Link>
          </div>
        </div>

        <div className="relative">
          <div className="overflow-hidden rounded-[2rem] bg-white shadow-lg">
            <Image
              src="/calma-hero.jpg"
              alt="Jabón Calma Verde sobre base de madera con hojas de moringa"
              width={1200}
              height={900}
              className="h-full w-full object-cover"
              priority
            />
          </div>
        </div>
      </section>

      {/* INTRO */}
      <section className="mx-auto max-w-7xl px-6 pb-6">
        <div className="rounded-[2rem] border border-[#e2dbcf] bg-[#f3eee5] px-6 py-8 md:px-10">
          <p className="text-sm uppercase tracking-[0.25em] text-green-700">
            Nuestra colección
          </p>
          <h2 className="mt-3 text-3xl font-semibold md:text-4xl">Productos</h2>
          <p className="mt-4 max-w-3xl text-base leading-7 text-[#4b5a4b]">
            Cuidado diario con moringa para una piel saludable, natural y en
            equilibrio.
          </p>
        </div>
      </section>

      {/* PRODUCTOS */}
      <section id="productos" className="mx-auto max-w-7xl px-6 py-10 md:py-14">
        <div className="grid gap-8 md:grid-cols-3">
          {products.map((product) => (
            <article
              key={product.name}
              className="overflow-hidden rounded-[2rem] border border-[#e2dbcf] bg-white shadow-sm transition hover:-translate-y-1 hover:shadow-md"
            >
              <div className="relative aspect-[4/3]">
                <Image
                  src={product.image}
                  alt={product.alt}
                  fill
                  className="object-cover"
                />
              </div>

              <div className="p-6">
                <h3 className="text-2xl font-semibold">{product.name}</h3>
                <p className="mt-2 text-lg font-medium text-green-700">
                  {product.price}
                </p>
                <p className="mt-4 text-sm leading-7 text-[#4b5a4b]">
                  {product.description}
                </p>

                <div className="mt-5 flex flex-wrap gap-2">
                  {product.tags.map((tag) => (
                    <span
                      key={tag}
                      className="rounded-full bg-[#eef3ea] px-3 py-1 text-xs font-medium text-[#355335]"
                    >
                      {tag}
                    </span>
                  ))}
                </div>

                <div className="mt-6">
                  <WhatsAppButton text="Consultar" />
                </div>
              </div>
            </article>
          ))}
        </div>
      </section>

      {/* GALERÍA / APOYO VISUAL */}
      <section className="mx-auto max-w-7xl px-6 py-6 md:py-10">
        <div className="grid gap-6 md:grid-cols-3">
          <div className="overflow-hidden rounded-[2rem] bg-white shadow-sm">
            <Image
              src="/detox-product.jpg"
              alt="Jabón Moringa Detox sobre base de madera"
              width={1200}
              height={900}
              className="h-full w-full object-cover"
            />
          </div>

          <div className="overflow-hidden rounded-[2rem] bg-white shadow-sm">
            <Image
              src="/vital-product.jpg"
              alt="Jabón Vital Skin sobre base de madera"
              width={1200}
              height={900}
              className="h-full w-full object-cover"
            />
          </div>

          <div className="overflow-hidden rounded-[2rem] bg-white shadow-sm">
            <Image
              src="/calma-pack.jpg"
              alt="Empaque de Calma Verde con el jabón"
              width={1200}
              height={900}
              className="h-full w-full object-cover"
            />
          </div>
        </div>
      </section>

      {/* NOSOTROS */}
      <section id="nosotros" className="mx-auto max-w-7xl px-6 py-14 md:py-20">
        <div className="grid gap-10 md:grid-cols-2 md:items-center">
          <div className="overflow-hidden rounded-[2rem] bg-white shadow-lg">
            <Image
              src="/calma-hero.jpg"
              alt="Calma Verde con hojas de moringa"
              width={1200}
              height={900}
              className="h-full w-full object-cover"
            />
          </div>

          <div>
            <p className="text-sm uppercase tracking-[0.25em] text-green-700">
              Nuestra historia
            </p>
            <h2 className="mt-3 text-3xl font-semibold md:text-4xl">
              Desde Costa Rica, para tu piel
            </h2>

            <p className="mt-6 text-base leading-8 text-[#4b5a4b]">
              En Moringa Viva CR creemos en el poder de la naturaleza. Nuestros
              productos nacen de la tierra costarricense, donde la moringa crece
              en armonía con el entorno tropical.
            </p>

            <p className="mt-4 text-base leading-8 text-[#4b5a4b]">
              Cada fórmula está diseñada para brindar un cuidado suave, natural y
              equilibrado, combinando la esencia de la moringa con una estética
              artesanal premium.
            </p>

            <p className="mt-4 text-base font-medium italic text-green-800">
              Naturaleza que se siente en tu piel.
            </p>
          </div>
        </div>
      </section>

      {/* BENEFICIOS */}
      <section className="mx-auto max-w-7xl px-6 pb-14 md:pb-20">
        <div className="grid gap-6 md:grid-cols-4">
          {[
            {
              title: "100% Natural",
              text: "Ingredientes seleccionados con enfoque natural y artesanal.",
            },
            {
              title: "Hecho con Amor",
              text: "Cada producto es elaborado con dedicación y cuidado.",
            },
            {
              title: "Moringa Viva",
              text: "La moringa inspira una línea pensada para el cuidado diario.",
            },
            {
              title: "Estilo Premium",
              text: "Presentación natural, elegante y coherente con tu marca.",
            },
          ].map((item) => (
            <div
              key={item.title}
              className="rounded-[2rem] border border-[#e2dbcf] bg-white p-6 shadow-sm"
            >
              <h3 className="text-lg font-semibold">{item.title}</h3>
              <p className="mt-3 text-sm leading-7 text-[#4b5a4b]">{item.text}</p>
            </div>
          ))}
        </div>
      </section>

      {/* CTA */}
      <section
        id="contacto"
        className="mx-auto max-w-7xl px-6 pb-14 md:pb-20"
      >
        <div className="rounded-[2rem] bg-[#244b2d] px-6 py-10 text-white md:px-10 md:py-14">
          <h2 className="text-3xl font-semibold md:text-4xl">
            Haz tu pedido o solicita información
          </h2>
          <p className="mt-4 max-w-2xl text-base leading-7 text-white/85">
            Estamos para ayudarte a elegir el jabón ideal para tu piel.
          </p>

          <div className="mt-8 flex flex-wrap gap-4">
            <Link
              href="https://wa.me/50672647175?text=Hola,%20quiero%20hacer%20un%20pedido%20de%20Moringa%20Viva%20CR"
              target="_blank"
              className="inline-flex items-center justify-center rounded-full bg-white px-5 py-3 text-sm font-semibold text-[#244b2d] transition hover:bg-[#f3eee5]"
            >
              WhatsApp · Respuesta rápida y personalizada
            </Link>

            <Link
              href="https://instagram.com/moringavivacr"
              target="_blank"
              className="inline-flex items-center justify-center rounded-full border border-white/30 px-5 py-3 text-sm font-semibold text-white transition hover:bg-white/10"
            >
              Instagram · @moringavivacr
            </Link>
          </div>

          <div className="mt-8 text-sm text-white/80">
            <p>Costa Rica</p>
            <p>Lun - Sáb: 7 hrs a 19 hrs</p>
          </div>
        </div>
      </section>

      {/* FOOTER */}
      <footer className="border-t border-[#d9d2c6] px-6 py-8">
        <div className="mx-auto flex max-w-7xl flex-col gap-2 text-sm text-[#4b5a4b] md:flex-row md:items-center md:justify-between">
          <div>
            <p className="font-semibold text-[#1f2a1f]">Moringa Viva CR</p>
            <p>Naturaleza que se siente en tu piel</p>
          </div>

          <div className="text-left md:text-right">
            <p>© 2026 Moringa Viva CR. Todos los derechos reservados.</p>
            <p>Hecho en Costa Rica</p>
          </div>
        </div>
      </footer>
    </main>
  );
}
