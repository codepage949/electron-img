# electron-img

## 예제

```python
import subprocess

with open("index.html", "w", encoding="utf-8") as f:
    f.write(f"""
        <!DOCTYPE html>
        <html>
            <head>
                <title>electron-img</title>
            </head>

            <body style="padding: 0px; margin: 0px;">
                <div id="electron-img" style="display: inline-flex;">
                    <!-- 주석 안쪽 부분을 자유롭게 수정하시면 됩니다 -->
                    <img src="./node_modules/electron-img/data.jpg" />
                    <div style="position: absolute; left: 0px; top: 0px; font-size: 50px;">test</div>
                    <!-- 주석 안쪽 부분을 자유롭게 수정하시면 됩니다 -->
                </div>

                <script src="./node_modules/electron-img/js_in_html.js"></script>
            </body>
        </html>
    """)

subprocess.run(
    [
        f"./node_modules/electron/dist/electron",
        f"./node_modules/electron-img/main.js",
        "--",
        f"./index.html",
    ]
)
```

실행 결과로 result.jpg 가 생성됩니다.
