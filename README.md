<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Khảo sát mức độ ảnh hưởng của mạng xã hội</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 20px;
            background-color: #f4f4f4;
        }
        .container {
            max-width: 800px;
            margin: 0 auto;
            background-color: white;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0,0,0,0.1);
        }
        h1 {
            text-align: center;
        }
        .question {
            margin: 20px 0;
        }
        .question label {
            display: block;
            margin-bottom: 10px;
        }
        .result {
            margin-top: 20px;
            text-align: center;
        }
        button {
            padding: 10px 20px;
            background-color: #007BFF;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }
        button:hover {
            background-color: #0056b3;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Khảo sát mức độ ảnh hưởng của mạng xã hội</h1>
        <form id="survey-form">
            <!-- Câu hỏi 1 -->
            <div class="question">
                <label>Tôi thường xuyên so sánh bản thân với người khác trên mạng xã hội.</label>
                <input type="radio" name="q1" value="1"> 1
                <input type="radio" name="q1" value="2"> 2
                <input type="radio" name="q1" value="3"> 3
                <input type="radio" name="q1" value="4"> 4
                <input type="radio" name="q1" value="5"> 5
            </div>
            <!-- Thêm các câu hỏi từ 2 đến 10 theo cùng cấu trúc -->
            <div class="question">
                <label>Số lượng lượt thích và bình luận trên bài đăng ảnh hưởng đến tâm trạng của tôi.</label>
                <input type="radio" name="q2" value="1"> 1
                <input type="radio" name="q2" value="2"> 2
                <input type="radio" name="q2" value="3"> 3
                <input type="radio" name="q2" value="4"> 4
                <input type="radio" name="q2" value="5"> 5
            </div>

            <!-- Các câu hỏi khác cũng tương tự -->

            <!-- Nút submit -->
            <button type="button" onclick="calculateScore()">Hoàn thành</button>
        </form>

        <!-- Kết quả sẽ hiển thị tại đây -->
        <div class="result" id="result"></div>
    </div>

    <script>
        function calculateScore() {
            // Lấy tất cả giá trị của các câu hỏi
            var totalScore = 0;
            for (var i = 1; i <= 10; i++) {
                var radios = document.getElementsByName('q' + i);
                for (var j = 0; j < radios.length; j++) {
                    if (radios[j].checked) {
                        totalScore += parseInt(radios[j].value);
                    }
                }
            }

            // Hiển thị tổng điểm
            var resultText = "";
            if (totalScore <= 20) {
                resultText = "Tổng điểm của bạn là " + totalScore + ". Bạn có cái tôi khá ổn định và ít bị ảnh hưởng bởi mạng xã hội.";
            } else if (totalScore <= 30) {
                resultText = "Tổng điểm của bạn là " + totalScore + ". Mức độ ảnh hưởng của mạng xã hội đối với cái tôi của bạn ở mức trung bình.";
            } else if (totalScore <= 40) {
                resultText = "Tổng điểm của bạn là " + totalScore + ". Bạn có xu hướng bị ảnh hưởng rõ rệt bởi mạng xã hội.";
            } else {
                resultText = "Tổng điểm của bạn là " + totalScore + ". Mạng xã hội có ảnh hưởng mạnh đến cái tôi và cảm giác tự tin của bạn.";
            }

            document.getElementById('result').innerHTML = resultText;
        }
    </script>
</body>
</html>
