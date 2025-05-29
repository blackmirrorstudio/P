# Создаём PDF с использованием стандартного шрифта и латиницей вместо кириллицы, чтобы избежать проблем кодировки

pdf = FPDF()
pdf.add_page()
pdf.set_font("Arial", size=12)

# Вставляем текст в латинице, имитируя структуру объявлений
ads_latin = [
    ("Example 1", "🚐 Nuzhen voditel s busom (7+ mest)\nMarshrut: UA → SK → DE\nDohod: ot 1200€ za reis\nNavigatsiya, podderzhka 24/7\nVyiezd — v techenie 48 ch\nZayavki — @euroroute_admin"),
    ("Example 2", "🧭 Rabota na kursakh: Vostochnaya Evropa\nAvto predostavlyaetsya\nVyezdy 2–3 raza v nedelyu\nDohod stabil'nyy, po faktu\nBezopasno, bez shtrafov\nZapis' — @go_driver24"),
    ("Example 3", "📦 Nuzhny voditeli na transfernye marshruty\nLT → PL → DE\nZP ot 1000–1500€/reis\nVse po marshrutam, bez pogruzok\nBez opyta — obuchim\nDokumenty ne nuzhny\nSvyaz': @transline_now"),
    ("Example 4", "🔒 Rabota dlya otvetstvennykh. Konfidentsial'no.\nPoezdki po marshrutam v ES\nBez lishnikh voprosov. Vse obyasnim.\nZP za den' — ot 500€\nOpyt privetstvuyetsya, no ne obyazatelen\nTelegram: @quiet_move2024")
]

for title, body in ads_latin:
    pdf.set_font("Arial", style='B', size=12)
    pdf.cell(0, 10, title, ln=True)
    pdf.set_font("Arial", size=11)
    pdf.multi_cell(0, 8, body)
    pdf.ln(5)

# Сохраняем PDF
output_path = "/mnt/data/Black_Recruiting_Driver_Ads.pdf"
pdf.output(output_path)

output_path
