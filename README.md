# RISC-V Multi-Cycle Controller Design

Bu proje, RISC-V mimarisine sahip çok vuruşlu (multi-cycle) bir işlemci kontrol ünitesinin SystemVerilog ile tasarımını ve QuestaSim üzerindeki test süreçlerini içermektedir.

## 🚀 Proje Özeti (Project Summary)
- **Mimari:** RISC-V Multi-cycle
- **Tasarım Dili:** SystemVerilog
- **Simülasyon:** QuestaSim
- **Test Kapsamı:** 40 Test Vektörü (R-Type, Load, Store, Branch, Jump)

## 📊 Simülasyon Sonuçları (Simulation Results)

### 1. Konsol Çıktısı (Transcript)
Simülasyon sonunda tüm test vektörleri başarıyla tamamlanmış ve tasarımın doğruluğu tescillenmiştir.
![Transcript 0 Error](transcript_0error.png) 
*(Not: Dosya sonu (EOF) nedeniyle oluşan son hata raporu dışında tüm 40 vektör başarıyla geçilmiştir.)*

### 2. Dalga Formu Analizi (Waveform)
Aşağıdaki görselde, işlemcinin `state` (durum) geçişlerini ve kontrol sinyallerinin zamanlamasını görebilirsiniz.
![Waveform](waveform.png)

## 🛠️ Teknik Detaylar (Technical Insights)
Tasarım sürecinde özellikle şu noktalar üzerinde durulmuştur:
- **FSM Tasarımı:** Komutların Fetch (0) aşamasından başlayarak ilgili Writeback veya Memory aşamalarına kadar olan geçişleri optimize edildi.
- **ALU Decoding:** Lab föyü (Harris & Harris) ile testbench (Patterson & Hennessy) arasındaki sinyal eşleme farkları analiz edilerek `aludec.sv` modülü güncellendi.
- **Hata Ayıklama:** Toplamda 6 saatlik bir çalışma ile 40 hata durumu analiz edildi ve "0 error" sonucuna ulaşıldı.

## 📂 Dosya Yapısı
- `mainfsm.sv`: Ana kontrol ünitesi (FSM)
- `aludec.sv`: ALU kontrol sinyallerini üreten dekoder
- `controller.sv`: Üst seviye kontrol modülü
- `testbench.sv`: Simülasyon ortamı