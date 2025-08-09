<!DOCTYPE html>
<html lang="zh-TW">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>互動式內容展示</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            line-height: 1.6;
            padding: 20px;
            max-width: 800px;
            margin: 0 auto;
        }

        .highlight-text {
            color: #007BFF;
            text-decoration: underline;
            cursor: pointer;
            font-weight: bold;
        }

        .description-container {
            border: 1px solid #ccc;
            border-radius: 10px;
            padding: 15px;
            margin-top: 10px;
            background-color: #f8f9fa;
            max-height: 0;
            overflow: hidden;
            transition: max-height 0.3s ease-out, padding 0.3s ease-out;
        }

        .description-container.active {
            max-height: 200px; /* 根據內容調整此值 */
            padding: 15px;
        }

        .description-text {
            color: #333;
            font-size: 14px;
        }
    </style>
</head>
<body>

    <p>
        現在共和黨在參議院握有53票（事實上包含<span id="highlighted-topic" class="highlight-text">副總統萬斯的一票</span>），眾議院握有219票。雖然單獨過半，但因為普通的立法程序在參議院需要60票同意，考量到現實兩黨對立，故而共和黨人啟動程序，預先設立預算決議案（budget resolution）。而通過此決議案無論在參眾兩院皆只需要過半數同意。因此在今年的2/25日決議案以217-215通過眾議院版本，一個半月後4/5則以51-48通過參議院版本，最後在4/10號兩院通過版本達成一致。
    </p>

    <div id="description-box" class="description-container">
        <p class="description-text">
            美國憲法規定副總統為參議院議長，但其職權有所限制，不能參與辯論或提出議案，只能在同意與不同意票平票時投下「關鍵性的一票」。歷史上最多次使用此一職責的為第49任副總統賀錦麗，在其任內一共使用了33次，主要原因為兩黨人數差距過小。
        </p>
    </div>

    <script>
        document.addEventListener('DOMContentLoaded', function() {
            const topicElement = document.getElementById('highlighted-topic');
            const descriptionBox = document.getElementById('description-box');

            topicElement.addEventListener('click', function() {
                descriptionBox.classList.toggle('active');
            });
        });
    </script>

</body>
</html>
