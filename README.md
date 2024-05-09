# electron-img

## 예제

1. npm install https://github.com/codepage949/electron-img
1. 아래 코드 내용으로 main.py 생성
    ```python
    import subprocess
    import platform

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

    if platform.system() == "Windows":
        subprocess.run(
            [
                f"./node_modules/electron/dist/electron.exe",
                f"./node_modules/electron-img/main.js",
                "--",
                f"./index.html",
            ]
        )
    elif platform.system() == "Darwin":
        subprocess.run(
            [
                f"./node_modules/electron/dist/Electron.app/Contents/MacOS/Electron",
                f"./node_modules/electron-img/main.js",
                "--",
                f"./index.html",
            ]
        )
    else:
        subprocess.run(
            [
                f"./node_modules/electron/dist/electron",
                f"./node_modules/electron-img/main.js",
                "--",
                f"./index.html",
            ]
        )
    ```
1. python main.py

실행 결과로 result.png 가 생성됩니다.
