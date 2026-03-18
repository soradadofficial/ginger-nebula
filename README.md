# 🌟 Ginger Nebula Quantum Grid EA
### เวอร์ชัน 2.10 Trial | Powered by SORADAD System

> **⚠️ สำคัญ:** กรุณาอ่านคู่มือนี้ทั้งหมดก่อนเริ่มใช้งาน เพื่อความปลอดภัยของเงินทุนและการใช้งานที่ถูกต้อง

---

## 📋 สารบัญ

1. [EA คืออะไร?](#ea-คืออะไร)
2. [ความต้องการของระบบ](#ความต้องการของระบบ)
3. [วิธีติดตั้ง EA](#วิธีติดตั้ง-ea)
4. [การยืนยันตัวตน (License)](#การยืนยันตัวตน-license)
5. [การตั้งค่าพารามิเตอร์](#การตั้งค่าพารามิเตอร์)
6. [การเชื่อมต่อ Telegram / Discord](#การเชื่อมต่อ-telegram--discord)
7. [Dashboard อ่านค่าอย่างไร?](#dashboard-อ่านค่าอย่างไร)
8. [คำแนะนำการตั้งค่าสำหรับมือใหม่](#คำแนะนำการตั้งค่าสำหรับมือใหม่)
9. [คำถามที่พบบ่อย (FAQ)](#คำถามที่พบบ่อย-faq)
10. [ติดต่อทีมงาน](#ติดต่อทีมงาน)


---

## ความต้องการของระบบ

| รายการ | รายละเอียด |
|--------|-----------|
| แพลตฟอร์ม | MetaTrader 5 (MT5) Build 3930 ขึ้นไป |
| คู่สกุลเงิน | XAUUSD (Gold) แนะนำ หรือคู่อื่นๆ ที่มีค่า Spread ต่ำ |
| Timeframe | M1, M5, M15 (แนะนำ M5) |
| เงินทุนขั้นต่ำ | $500 ขึ้นไป (สำหรับ Lot 0.01) |
| อินเทอร์เน็ต | ต้องการตลอดเวลา (สำหรับ License Verification) |
| บัญชี | Demo หรือ Real Account (ECN แนะนำ) |

---

## วิธีติดตั้ง EA

### ขั้นตอนที่ 1: คัดลอกไฟล์

1. เปิด **MetaTrader 5**
2. ไปที่เมนู **File → Open Data Folder**
3. เปิดโฟลเดอร์ `MQL5 → Experts`
4. **วางไฟล์** `Ginger_Nebula_Quantum.ex5` ลงในโฟลเดอร์นี้

```
📁 MT5 Data Folder/
└── 📁 MQL5/
    └── 📁 Experts/
        └── ✅ Ginger_Nebula_Quantum.ex5  ← วางไฟล์ที่นี่
```

### ขั้นตอนที่ 2: อนุญาต WebRequest (สำคัญมาก!)

> EA ต้องเชื่อมต่ออินเทอร์เน็ตเพื่อยืนยัน License หากไม่ทำขั้นตอนนี้ EA จะไม่ทำงาน

1. ไปที่ **Tools → Options → Expert Advisors**
2. ✅ เปิดใช้งาน **"Allow WebRequest for listed URL"**
3. เพิ่ม URL ต่อไปนี้:
   - `https://soradad.com`
4. กด **OK** แล้ว **Restart MT5**

### ขั้นตอนที่ 3: ลาก EA ลงชาร์ท

1. เปิดชาร์ท **XAUUSD** หรือคู่ที่ต้องการ
2. ในหน้าต่าง **Navigator** ด้านซ้าย → ค้นหา `Ginger_Nebula_Quantum`
3. **ลากลงบนชาร์ท**
4. หน้าต่าง Settings จะเปิดขึ้น → ตั้งค่าตามส่วนถัดไป
5. กด **OK**
6. ตรวจสอบว่ามีสัญลักษณ์ **😊 (หน้ายิ้ม)** ที่มุมบนขวาของชาร์ท และเปิด **Auto Trading** ✅

---

## การยืนยันตัวตน (License)

EA ใช้ระบบ License ผ่าน SORADAD Platform

### วิธีหา User ID

1. เข้าเว็บไซต์ **[soradad.com](https://soradad.com)**
2. Log in เข้าบัญชีของคุณ
3. ไปที่หน้า **"โปรไฟล์"** หรือ **"Profile"**
4. คัดลอก **User ID** ของคุณ

### กรอก User ID ใน EA

| Parameter | ค่าที่ต้องกรอก |
|-----------|--------------|
| `InpSoraDadUserID` | User ID ที่ได้จากหน้าโปรไฟล์ |
| `InpPortfolioID` | Portfolio ID ที่สร้างในระบบ |
| `InpAPIKey` | ใช้ค่า default ได้เลย: `soradad-mt5-2026` |

> 💡 **ถ้า EA แจ้ง License Error**: ตรวจสอบว่ากรอก User ID ถูกต้อง และ Account Number ของคุณได้รับการอนุมัติในระบบแล้ว

---

## การตั้งค่าพารามิเตอร์

### 📌 Portfolio Identification

| Parameter | ความหมาย | ตัวอย่าง |
|-----------|---------|---------|
| `InpPortfolioName` | ชื่อพอร์ตที่แสดงใน Dashboard | `"GN-GOLD-01"` |
| `InpPortfolioID` | ID พอร์ตจากระบบ SORADAD | `"ABC123"` |
| `InpSoraDadUserID` | User ID สำหรับยืนยันตัวตน | ดูในหน้าโปรไฟล์ |

---

### 📌 Trading Direction (ทิศทางการเทรด)

| ตัวเลือก | ความหมาย |
|---------|---------|
| `Buy Only` | EA เปิดแค่ BUY เท่านั้น |
| `Sell Only` | EA เปิดแค่ SELL เท่านั้น |
| `Both` | EA เปิดทั้ง BUY และ SELL (ค่าเริ่มต้น) |

---

### 📌 Money Management (จัดการเงินทุน)

| Parameter | ความหมาย | แนะนำ |
|-----------|---------|-------|
| `InpLotStart` | ล็อตแรกที่เปิด | `0.01` (ถ้าทุน $500) |
| `InpLotMultiplier` | ตัวคูณล็อตเมื่อเพิ่ม Grid | `1.5` - `2.0` |
| `InpMaxOrders` | จำนวนไม้สูงสุด | `5` - `10` ไม้ |

> ⚠️ **คำเตือน:** `InpLotMultiplier` ยิ่งสูง กำไรยิ่งมาก แต่ความเสี่ยงก็สูงตามด้วย แนะนำ `1.5` สำหรับผู้เริ่มต้น

---

### 📌 Grid Settings (การตั้งค่า Grid)

| Parameter | ความหมาย | แนะนำ |
|-----------|---------|-------|
| `InpGridStep` | ระยะห่างระหว่างแต่ละ Grid (Points) | XAUUSD: `300-500` |
| `InpTargetProfit` | กำไรเป้าหมายรวม ($) ต่อรอบ | `$5` - `$20` |

> 💡 **Point** ≠ **Pip** → สำหรับ XAUUSD: 1 pip = 10 points

---

### 📌 Exit Settings (การออกจากตลาด)

| Parameter | ความหมาย | แนะนำ |
|-----------|---------|-------|
| `InpUseIndividualExit` | เปิด TP/SL แยกแต่ละไม้ | `false` (ค่าเริ่มต้น) |
| `InpTPPoints` | Take Profit ต่อไม้ (Points) | `500` |
| `InpSLPoints` | Stop Loss ต่อไม้ (Points) | `1000` |

> 💡 แนะนำปิด `InpUseIndividualExit` และใช้ `InpTargetProfit` แทน เพราะ Grid ทำงานได้ดีกว่าแบบ Basket Close

---

### 📌 Risk Management (ป้องกันความเสี่ยง)

| Parameter | ความหมาย | แนะนำ |
|-----------|---------|-------|
| `InpUseDrawdownProtection` | เปิดระบบพักกันขาดทุน | `true` |
| `InpMaxDailyLoss` | ขาดทุนสูงสุดต่อวัน ($) | 5-10% ของทุน |
| `InpMaxFloatingLoss` | ขาดทุน Floating สูงสุด ($) | 10-20% ของทุน |
| `InpStopEquityPercent` | หยุดเมื่อ Equity เหลือ (%) | `70` - `80` |

---

### 📌 Spike Filter (กรองราคาผิดปกติ)

| Parameter | ความหมาย | แนะนำ |
|-----------|---------|-------|
| `InpUseSpikeFilter` | เปิดกรอง Spike | `true` |
| `InpSpikePoints` | ระยะ Spike สูงสุดที่ยอมรับ (Points) | `500` |
| `InpSpikeCooldown` | หยุดเทรดหลัง Spike (นาที) | `5` |

---

### 📌 Time Filter (กรองเวลาเทรด)

| Parameter | ความหมาย | แนะนำ |
|-----------|---------|-------|
| `InpUseTimeFilter` | เปิดกรองเวลา | `true` |
| `InpStartHour` | เริ่มเทรด (Server Time) | `2` |
| `InpEndHour` | หยุดเทรด (Server Time) | `22` |
| `InpAvoidFriday` | หลีกเลี่ยงเทรดวันศุกร์ | `true` |
| `InpFridayCloseHour` | ปิดออเดอร์วันศุกร์เวลา | `20` |

> 💡 **Server Time** คือเวลาของ Broker ไม่ใช่เวลาไทย ให้ดูจากชาร์ท MT5 ของคุณ

---

## การเชื่อมต่อ Telegram / Discord

### 📱 Telegram Bot

EA สามารถส่งแจ้งเตือนไปยัง Telegram ได้อัตโนมัติ

1. สร้าง Bot ผ่าน **[@BotFather](https://t.me/BotFather)** แล้วรับ **Bot Token**
2. หา **Chat ID** ของคุณจาก **[@userinfobot](https://t.me/userinfobot)**
3. กรอกใน EA:
   - `InpUseTelegram` = `true`
   - `InpTelegramToken` = Token ที่ได้จาก BotFather
   - `InpTelegramChatID` = Chat ID ของคุณ

### 💬 Discord Webhook

1. ไปที่ Server Settings ของ Discord → **Integrations → Webhooks**
2. สร้าง Webhook ใหม่ แล้วคัดลอก URL
3. กรอกใน EA:
   - `InpUseDiscord` = `true`
   - `InpDiscordWebhook` = Webhook URL ที่คัดลอกมา

---

### 📊 Hourly Report

| Parameter | ความหมาย |
|-----------|---------|
| `InpSendHourlyReport` | เปิดส่งสรุปผลตามรอบ |
| `InpReportInterval` | ช่วงเวลาส่งรายงาน (นาที) ค่าปกติ = 60 |

---

## Dashboard อ่านค่าอย่างไร?

```
┌─────────────────────────────────┐
│   GINGER NEBULA                 │
│   QUANTUM GRID          v2.10   │
├─────────────────────────────────┤
│ ACCOUNT                         │
│   Balance:       $1,000.00      │
│   Equity:        $1,020.00      │
│   Free Margin:   $800.00        │
├─────────────────────────────────┤
│ TRADING STATUS                  │
│   Floating P/L:  +$20.00  🟢   │
│   Buy:    2 (0.15 lots)         │
│   Sell:   0 (0.00 lots)         │
│   Total:  2 (0.15 lots)         │
├─────────────────────────────────┤
│ TARGET PROGRESS  [████░░] 65%   │
│   $13 / $20                     │
├─────────────────────────────────┤
│ SYSTEM STATUS                   │
│   Direction:     BUY & SELL     │
│   Grid Step:     300 pts        │
│   Spike Filter:  ✅ ON          │
│   Time Filter:   ✅ ON          │
│   DD Protect:    ✅ ON          │
│   Daily Loss:    $5 / $100      │
├─────────────────────────────────┤
│   Running:   2h 30m             │
│   Updated:   12:45:30           │
└─────────────────────────────────┘
```

| ส่วนที่แสดง | ความหมาย |
|-----------|---------|
| **Balance** | ยอดเงินในบัญชี |
| **Equity** | ยอดเงิน + กำไร/ขาดทุน Floating |
| **Floating P/L** | กำไร/ขาดทุนปัจจุบัน (ยังไม่ปิดออเดอร์) |
| **Target Progress** | ความคืบหน้าไปถึงเป้ากำไรรอบนี้ |
| **Daily Loss** | ขาดทุนวันนี้เทียบกับที่ตั้งไว้ |

---

## คำแนะนำการตั้งค่าสำหรับมือใหม่

### 🟢 Conservative (ความเสี่ยงต่ำ)
เหมาะสำหรับทุน $500 - $1,000

| Parameter | ค่าแนะนำ |
|-----------|---------|
| `InpLotStart` | `0.01` |
| `InpLotMultiplier` | `1.5` |
| `InpMaxOrders` | `5` |
| `InpGridStep` | `500` |
| `InpTargetProfit` | `$5` |
| `InpMaxDailyLoss` | `$30` |
| `InpMaxFloatingLoss` | `$50` |

### 🟡 Moderate (ความเสี่ยงปานกลาง)
เหมาะสำหรับทุน $1,000 - $3,000

| Parameter | ค่าแนะนำ |
|-----------|---------|
| `InpLotStart` | `0.05` |
| `InpLotMultiplier` | `1.8` |
| `InpMaxOrders` | `7` |
| `InpGridStep` | `400` |
| `InpTargetProfit` | `$15` |
| `InpMaxDailyLoss` | `$80` |
| `InpMaxFloatingLoss` | `$150` |

### 🔴 Aggressive (ความเสี่ยงสูง)
เหมาะสำหรับทุน $3,000 ขึ้นไป

| Parameter | ค่าแนะนำ |
|-----------|---------|
| `InpLotStart` | `0.1` |
| `InpLotMultiplier` | `2.0` |
| `InpMaxOrders` | `10` |
| `InpGridStep` | `300` |
| `InpTargetProfit` | `$30` |
| `InpMaxDailyLoss` | `$200` |
| `InpMaxFloatingLoss` | `$400` |

> ⚠️ **แนะนำ: ทดสอบบน Demo Account ก่อนใช้งานจริงเสมอ**

---

## คำถามที่พบบ่อย (FAQ)

**Q: EA ไม่เปิดออเดอร์เลย ทำไม?**
> A: ตรวจสอบ (1) เปิด Auto Trading แล้วหรือยัง (2) ตั้ง Time Filter ถูกต้องหรือไม่ (3) Stochastic ยังไม่ให้สัญญาณ

**Q: EA แจ้ง "License Error" ทำอย่างไร?**
> A: ตรวจสอบว่า `InpSoraDadUserID` กรอกถูกต้อง และเพิ่ม URL ใน WebRequest แล้ว ถ้ายังไม่ได้ผลติดต่อทีมงาน

**Q: Dashboard ไม่แสดง?**
> A: ตรวจสอบว่า `InpShowDashboard = true` และ Chart ไม่ได้อยู่ในโหมด Dark ที่ซ่อนหน้าต่าง

**Q: EA ปิดออเดอร์เองแบบไม่คาดคิด?**
> A: ระบบ Drawdown Protection ทำงาน ตรวจสอบค่า `InpMaxDailyLoss` และ `InpMaxFloatingLoss` ว่าตั้งไว้เหมาะสมหรือไม่

**Q: ควรรัน EA บนกี่คู่เงิน?**
> A: แนะนำ 1 EA ต่อ 1 คู่เงิน และตั้ง `InpMagicNum` ให้ต่างกันในแต่ละชาร์ท

**Q: ทดสอบ Backtest ได้ไหม?**
> A: ได้ครับ EA รองรับ Strategy Tester ของ MT5 (ระบบ License จะข้ามการตรวจสอบใน Tester mode อัตโนมัติ)

---

## ติดต่อทีมงาน

| ช่องทาง | รายละเอียด |
|---------|-----------|
| 🌐 Website | [soradad.com](https://soradad.com) |
| 📧 Email | support@soradad.com |
| 💬 Line / Telegram | ติดต่อผ่านเว็บไซต์ |

---

## ⚖️ ข้อตกลงและข้อจำกัดความรับผิดชอบ

- การเทรด Forex และ Gold มีความเสี่ยงสูง อาจสูญเสียเงินทุนทั้งหมดได้
- ผลการดำเนินงานในอดีตไม่ได้รับประกันผลในอนาคต
- **กรุณาทดสอบบน Demo Account ก่อนใช้งานจริงเสมอ**
- EA นี้เป็นเพียงเครื่องมือช่วย ผู้ใช้ต้องรับผิดชอบการตัดสินใจเทรดด้วยตนเอง

---

<div align="center">

**🌟 Ginger Nebula Quantum Grid EA**  
*Professional Grid Trading System*  
Powered by **SORADAD System** | v2.10 Trial

</div>
