<!DOCTYPE html>
<html lang="vi">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Đăng ký khám bệnh online</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 40px;
    }
    h1 {
      color: #0057a3;
    }
    form {
      max-width: 500px;
    }
    label {
      display: block;
      margin-top: 15px;
    }
    input, select, textarea {
      width: 100%;
      padding: 8px;
      margin-top: 5px;
    }
    button {
      margin-top: 20px;
      padding: 10px 20px;
      background-color: #0057a3;
      color: white;
      border: none;
      cursor: pointer;
    }
  </style>
</head>
<body>

  <h1>Đăng ký khám bệnh online</h1>

  <form id="registrationForm">
    <label>Họ tên:</label>
    <input type="text" id="name" required />

    <label>Ngày sinh:</label>
    <input type="date" id="dob" required />

    <label>Số điện thoại:</label>
    <input type="tel" id="phone" required />

    <label>Bác sĩ khám:</label>
    <select id="doctor" required>
      <option value="">-- Chọn bác sĩ --</option>
      <option value="BS. Sầm Huyền Sanh">BS. Sầm Huyền Sanh</option>
      <option value="BS. Trịnh Hồng Bắc">BS. Trịnh Hồng Bắc</option>
      <option value="BS. Lê Văn C">BS. Lê Văn C</option>
    </select>

    <label>Ngày khám:</label>
    <input type="date" id="examDate" required />

    <label>Ghi chú thêm:</label>
    <textarea id="note" rows="3"></textarea>

    <button type="submit">Gửi đăng ký</button>
  </form>

  <p id="resultMessage" style="color: green; margin-top: 20px;"></p>

  <script>
    const form = document.getElementById("registrationForm");
    const resultMessage = document.getElementById("resultMessage");

    form.addEventListener("submit", function (e) {
      e.preventDefault();

      const name = document.getElementById("name").value;
      const phone = document.getElementById("phone").value;
      const doctor = document.getElementById("doctor").value;
      const rawDate = new Date(document.getElementById("examDate").value);
      const examDate = rawDate.toLocaleDateString('vi-VN'); // dd/mm/yyyy

      resultMessage.textContent = `✅ Cảm ơn ${name}! Bạn đã đăng ký khám với ${doctor} vào ngày ${examDate}. Chúng tôi sẽ liên hệ với bạn qua số ${phone}.`;

      form.reset();
    });
  </script># BENH-VIEN-YDCT-KIEN-GIANG
