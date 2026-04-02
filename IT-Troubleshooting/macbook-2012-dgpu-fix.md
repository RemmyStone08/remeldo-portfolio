# 🛠️ MacBook Pro 2012 dGPU Failure Fix

## 📌 Overview

Diagnosed and resolved a **no-display boot issue** on a MacBook Pro (15-inch, Mid 2012) caused by a failing dedicated GPU.

---

## 💻 Device

* **Model:** MacBook Pro (15-inch, Mid 2012)
* **iGPU:** Intel HD Graphics 4000
* **dGPU:** NVIDIA GeForce GT 650M

---

## ⚠️ Symptoms

* Black screen on boot
* Backlight active
* Caps Lock responsive
* No external display output

---

## 🧠 Diagnosis

The system uses **automatic GPU switching**.

Failure of the **GT650M** causes the system to attempt initialization of a non-functional GPU, resulting in no video output.

---

## 🛠️ Fix — Force Integrated GPU

### Method: macOS Recovery

1. Boot into recovery
   `Command + R`

2. Open Terminal
   `Utilities → Terminal`

3. Run:

```bash
nvram fa4ce28d-b62f-4c99-9cc3-6815686e30f9:gpu-power-prefs=%01%00%00%00
```

4. Reboot:

```bash
reboot
```

---

### Fallback: Single User Mode

1. Boot
   `Command + S`

2. Run:

```bash
nvram fa4ce28d-b62f-4c99-9cc3-6815686e30f9:gpu-power-prefs=%01%00%00%00
reboot
```

---

## 🔁 Prevention

Use **gfxCardStatus** → `Integrated Only`

---

## ⚠️ Notes

* Workaround only (hardware fault remains)
* PRAM/NVRAM reset may undo fix
* Reduced GPU performance

---

## 🔧 Permanent Options

* Disable dGPU power rail
* OpenCore GPU block
* Logic board replacement

---

## 🧾 Result

System successfully booted using integrated graphics, restoring full usability.

---

## 👤 Author

**Remmy**
IT Support | Hardware Troubleshooting | Blue Team Path
