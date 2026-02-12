# Stored Cross-Site Scripting in Horilla CRM (≤ 1.0.2)
<table>
  <tr>
    <td width="150" rowspan="2">
      <a href="https://www.horilla.com/" target="_blank">
        <img src="https://avatars.githubusercontent.com/u/131998600?v=4" alt="Horilla CRM Logo" width="120"/>
      </a>
    </td>
    <td>
      <h1>Horilla CRM</h1>
      <h3> A free and open source CRM software.</h3>
    </td>
  </tr>
  <tr>
    <td>
      <table>
        <tr>
          <td>
            🔗 <a href="https://github.com/horilla-opensource/horilla-crm" target="_blank">Horilla CRM Github Repository</span></a>
          </td>
          <td style="padding-left: 15px;">
            🚀 <a href="https://github.com/horilla-opensource/horilla-crm/releases/tag/1.0.3" target="_blank"> Patched Version (v1.0.3) </span></a>
          </td>
        </tr>
      </table>
    </td>
  </tr>
</table>

## 📜 Description
Horilla CRM ≤ v1.0.2 contains a Stored Cross-Site Scripting (XSS) vulnerability in the Leads Notes functionality, allowing authenticated attackers to inject and execute arbitrary JavaScript.

## 🔍 Affected Versions

| Status       | Version         |
|--------------|-----------------|
| 🔴 Vulnerable |  ≤ `1.0.2`      |
| 🟢  Fixed     |  &nbsp;&nbsp;`1.0.3`      |   

## 🛠️ Steps to Reproduce

#### 1️⃣ Navigate to:
Leads → Select an existing Lead → Notes and Attachment → Add

<img src="/xss_payload.png" >

#### 2️⃣ Enter a title

#### 3️⃣ In the Notes field, manually type:
```
<img src=x onerror=alert('XSS')>
```
#### 4️⃣ Click Save
#### 5️⃣ Click the Edit (pencil) icon for the created note
#### 6️⃣ The injected JavaScript executes:
<img src="/xss_trigger.png">

## ⚠️ Disclaimer
This project is intended for **educational and ethical research purposes only**. Unauthorized testing on systems without explicit permission is illegal. Use responsibly and only on systems you own or have permission to test.

## 🧑‍💻 Discovery

This vulnerability was discovered by **Alex Perrakis** (Stolichnayer).

## 🔗 References:
- [Horilla CRM Github Repository](https://github.com/horilla-opensource/horilla-crm)
- [Patched Version (v1.0.3)](https://github.com/horilla-opensource/horilla-crm/releases/tag/1.0.3)
- [Fix Commit](https://github.com/horilla-opensource/horilla-crm/commit/730b5a44ff060916780c44a4bdbc8ced70a2cd27)
