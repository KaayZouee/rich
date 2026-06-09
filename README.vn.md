[![Phiên bản Python được hỗ trợ](https://img.shields.io/pypi/pyversions/rich)](https://pypi.org/project/rich/) [![Phiên bản PyPI](https://badge.fury.io/py/rich.svg)](https://badge.fury.io/py/rich)

[![Lượt tải](https://pepy.tech/badge/rich/month)](https://pepy.tech/project/rich)
[![codecov](https://img.shields.io/codecov/c/github/Textualize/rich?label=codecov&logo=codecov)](https://codecov.io/gh/Textualize/rich)
[![Blog Rich](https://img.shields.io/badge/blog-rich%20news-yellowgreen)](https://www.willmcgugan.com/tag/rich/)
[![Theo dõi Twitter](https://img.shields.io/twitter/follow/willmcgugan.svg?style=social)](https://twitter.com/willmcgugan)

![Logo](https://github.com/textualize/rich/raw/master/imgs/logo.svg)

[English readme](https://github.com/textualize/rich/blob/master/README.md)
 • [简体中文 readme](https://github.com/textualize/rich/blob/master/README.cn.md)
 • [正體中文 readme](https://github.com/textualize/rich/blob/master/README.zh-tw.md)
 • [Lengua española readme](https://github.com/textualize/rich/blob/master/README.es.md)
 • [Deutsche readme](https://github.com/textualize/rich/blob/master/README.de.md)
 • [Läs på svenska](https://github.com/textualize/rich/blob/master/README.sv.md)
 • [日本語 readme](https://github.com/textualize/rich/blob/master/README.ja.md)
 • [한국어 readme](https://github.com/textualize/rich/blob/master/README.kr.md)
 • [Français readme](https://github.com/textualize/rich/blob/master/README.fr.md)
 • [Schwizerdütsch readme](https://github.com/textualize/rich/blob/master/README.de-ch.md)
 • [हिन्दी readme](https://github.com/textualize/rich/blob/master/README.hi.md)
 • [Português brasileiro readme](https://github.com/textualize/rich/blob/master/README.pt-br.md)
 • [Italian readme](https://github.com/textualize/rich/blob/master/README.it.md)
 • [Русский readme](https://github.com/textualize/rich/blob/master/README.ru.md)
 • [Indonesian readme](https://github.com/textualize/rich/blob/master/README.id.md)
 • [فارسی readme](https://github.com/textualize/rich/blob/master/README.fa.md)
 • [Türkçe readme](https://github.com/textualize/rich/blob/master/README.tr.md)
 • [Polskie readme](https://github.com/textualize/rich/blob/master/README.pl.md)
 • [Tiếng Việt readme](https://github.com/textualize/rich/blob/master/README.vn.md)


Rich là một thư viện Python dùng để hiển thị văn bản _giàu định dạng_ (rich text) và định dạng đẹp trong terminal.

[Rich API](https://rich.readthedocs.io/en/latest/) giúp bạn dễ dàng thêm màu sắc và kiểu chữ cho đầu ra của terminal. Rich có thể hiển thị bảng, thanh tiến trình, markdown, mã nguồn có tô sáng cú pháp, tracebacks (và nhiều hơn nữa) rất đẹp — tất cả đều có sẵn ngay sau khi cài đặt, không cần cấu hình gì thêm.

![Tính năng](https://github.com/textualize/rich/raw/master/imgs/features.png)

Xem video giới thiệu về Rich tại [calmcode.io](https://calmcode.io/rich/introduction.html) bởi [@fishnets88](https://twitter.com/fishnets88).

Xem [mọi người nói gì về Rich](https://www.willmcgugan.com/blog/pages/post/rich-tweets/).

## Tương thích

Rich hoạt động trên Linux, macOS và Windows. Màu thật / emoji hoạt động trên Windows Terminal mới; terminal cổ điển bị giới hạn 16 màu. Rich yêu cầu Python 3.8 trở lên.

Rich hoạt động với [Jupyter notebooks](https://jupyter.org/) mà không cần cấu hình thêm.

## Cài đặt

Cài đặt bằng `pip` hoặc trình quản lý gói PyPI mà bạn ưa thích.

```sh
python -m pip install rich
```

Chạy lệnh sau để kiểm tra đầu ra của Rich trong terminal của bạn:

```sh
python -m rich
```

## Rich Print

Để dễ dàng thêm rich output vào ứng dụng của bạn, bạn có thể import hàm [rich print](https://rich.readthedocs.io/en/latest/introduction.html#quick-start), hàm này có signature giống với hàm `print` mặc định của Python. Hãy thử:

```python
from rich import print

print("Hello, [bold magenta]World[/bold magenta]!", ":vampire:", locals())
```

![Hello World](https://github.com/textualize/rich/raw/master/imgs/print.png)

## Rich REPL

Rich có thể được cài đặt vào Python REPL để mọi cấu trúc dữ liệu đều được pretty print và highlighted.

```python
>>> from rich import pretty
>>> pretty.install()
```

![REPL](https://github.com/textualize/rich/raw/master/imgs/repl.png)

## Sử dụng Console

Để kiểm soát nội dung terminal tốt hơn, hãy import và tạo một đối tượng [Console](https://rich.readthedocs.io/en/latest/reference/console.html#rich.console.Console).

```python
from rich.console import Console

console = Console()
```

Đối tượng Console có phương thức `print` với giao diện giống với hàm `print` mặc định. Sau đây là ví dụ sử dụng:

```python
console.print("Hello", "World!")
```

Đúng như dự đoán, đoạn code này sẽ in ra `"Hello World!"` trong terminal. Tuy nhiên, cần lưu ý rằng, khác với hàm `print` mặc định, Rich sẽ tự động xuống dòng văn bản để vừa với chiều rộng terminal.

Có một vài cách để thêm màu sắc và kiểu chữ cho đầu ra của bạn. Bạn có thể đặt style cho toàn bộ đầu ra bằng cách thêm tham số `style`. Ví dụ:

```python
console.print("Hello", "World!", style="bold red")
```

Đầu ra sẽ trông như sau:

![Hello World](https://github.com/textualize/rich/raw/master/imgs/hello_world.png)

Cách này phù hợp để tạo kiểu cho một dòng văn bản. Để tạo kiểu chi tiết hơn, Rich cung cấp một dạng markup đặc biệt có cú pháp tương tự [bbcode](https://en.wikipedia.org/wiki/BBCode). Ví dụ:

```python
console.print("Where there is a [bold cyan]Will[/bold cyan] there [u]is[/u] a [i]way[/i].")
```

![Console Markup](https://github.com/textualize/rich/raw/master/imgs/where_there_is_a_will.png)

Bạn có thể sử dụng đối tượng Console để tạo ra đầu ra tinh vi với rất ít công sức. Xem tài liệu [Console API](https://rich.readthedocs.io/en/latest/console.html) để biết thêm chi tiết.

## Rich Inspect

Rich có một hàm [inspect](https://rich.readthedocs.io/en/latest/reference/init.html?highlight=inspect#rich.inspect) giúp tạo báo cáo về bất kỳ đối tượng Python nào, chẳng hạn như class, instance, hoặc built-in.

```python
>>> my_list = ["foo", "bar"]
>>> from rich import inspect
>>> inspect(my_list, methods=True)
```

![Log](https://github.com/textualize/rich/raw/master/imgs/inspect.png)

Xem [tài liệu inspect](https://rich.readthedocs.io/en/latest/reference/init.html#rich.inspect) để biết chi tiết.

# Thư viện Rich

Rich chứa các _renderables_ built-in mà bạn có thể dùng để tạo ra đầu ra thanh lịch trong CLI và giúp gỡ lỗi code của mình.

Nhấp vào các tiêu đề dưới đây để xem chi tiết:

<details>
<summary>Log</summary>

Đối tượng Console có phương thức `log()` với giao diện tương tự `print()`, nhưng đồng thời hiển thị một cột chứa thời gian hiện tại cùng tên file và dòng đã gọi. Theo mặc định, Rich sẽ tô sáng cú pháp cho các cấu trúc Python và chuỗi repr. Nếu bạn log một collection (ví dụ dict hoặc list), Rich sẽ pretty print nó để vừa với không gian có sẵn. Dưới đây là ví dụ về một số tính năng này.

```python
from rich.console import Console
console = Console()

test_data = [
    {"jsonrpc": "2.0", "method": "sum", "params": [None, 1, 2, 4, False, True], "id": "1",},
    {"jsonrpc": "2.0", "method": "notify_hello", "params": [7]},
    {"jsonrpc": "2.0", "method": "subtract", "params": [42, 23], "id": "2"},
]

def test_log():
    enabled = False
    context = {
        "foo": "bar",
    }
    movies = ["Deadpool", "Rise of the Skywalker"]
    console.log("Hello from", console, "!")
    console.log(test_data, log_locals=True)


test_log()
```

Đoạn code trên tạo ra đầu ra sau:

![Log](https://github.com/textualize/rich/raw/master/imgs/log.png)

Lưu ý: tham số `log_locals` xuất ra một bảng chứa các biến cục bộ tại nơi phương thức log được gọi.

Phương thức log có thể dùng để ghi log ra terminal cho các ứng dụng chạy dài như máy chủ, nhưng cũng là một debugger rất hữu ích.

</details>
<details>
<summary>Logging Handler</summary>

Bạn cũng có thể sử dụng [lớp Handler](https://rich.readthedocs.io/en/latest/logging.html) built-in để định dạng và tô màu đầu ra từ module logging của Python. Sau đây là ví dụ đầu ra:

![Logging](https://github.com/textualize/rich/raw/master/imgs/logging.png)

</details>

<details>
<summary>Emoji</summary>

Để chèn một emoji vào đầu ra console, hãy đặt tên của nó giữa hai dấu hai chấm. Ví dụ:

```python
>>> console.print(":smiley: :vampire: :pile_of_poo: :thumbs_up: :raccoon:")
😃 🧛 💩 👍 🦝
```

Hãy sử dụng tính năng này một cách khôn ngoan.

</details>

<details>
<summary>Bảng (Tables)</summary>

Rich có thể hiển thị các [bảng](https://rich.readthedocs.io/en/latest/tables.html) linh hoạt với các ký tự unicode. Có rất nhiều tùy chọn định dạng cho viền, kiểu, căn chỉnh ô, v.v.

![table movie](https://github.com/textualize/rich/raw/master/imgs/table_movie.gif)

Hình ảnh động ở trên được tạo bằng [table_movie.py](https://github.com/textualize/rich/blob/master/examples/table_movie.py) trong thư mục examples.

Đây là ví dụ bảng đơn giản hơn:

```python
from rich.console import Console
from rich.table import Table

console = Console()

table = Table(show_header=True, header_style="bold magenta")
table.add_column("Date", style="dim", width=12)
table.add_column("Title")
table.add_column("Production Budget", justify="right")
table.add_column("Box Office", justify="right")
table.add_row(
    "Dec 20, 2019", "Star Wars: The Rise of Skywalker", "$275,000,000", "$375,126,118"
)
table.add_row(
    "May 25, 2018",
    "[red]Solo[/red]: A Star Wars Story",
    "$275,000,000",
    "$393,151,347",
)
table.add_row(
    "Dec 15, 2017",
    "Star Wars Ep. VIII: The Last Jedi",
    "$262,000,000",
    "[bold]$1,332,539,889[/bold]",
)

console.print(table)
```

Kết quả như sau:

![table](https://github.com/textualize/rich/raw/master/imgs/table.png)

Lưu ý: markup của console được hiển thị y hệt như trong `print()` và `log()`. Thực tế, **bạn có thể cho** bất kỳ thứ gì Rich hiển thị được vào header hoặc hàng — kể cả một bảng khác.

Lớp `Table` đủ thông minh để thay đổi kích thước cột cho phù hợp với chiều rộng terminal, tự động xuống dòng khi cần. Cũng ví dụ đó, nhưng với terminal nhỏ hơn bảng bên trên:

![table2](https://github.com/textualize/rich/raw/master/imgs/table2.png)

</details>

<details>
<summary>Thanh tiến trình (Progress Bars)</summary>

Rich có thể hiển thị nhiều [thanh tiến trình](https://rich.readthedocs.io/en/latest/progress.html) không nhấp nháy để theo dõi các tác vụ chạy dài.

Đối với tác vụ cơ bản, hãy bọc bất kỳ một dãy nào trong hàm `track` và lặp qua kết quả. Ví dụ:

```python
from rich.progress import track

for step in track(range(100)):
    do_step(step)
```

Việc thêm nhiều thanh tiến trình cũng không khó hơn là bao. Đây là ví dụ lấy từ tài liệu:

![progress](https://github.com/textualize/rich/raw/master/imgs/progress.gif)

Các cột có thể được cấu hình để hiển thị bất kỳ chi tiết nào bạn muốn. Các cột built-in bao gồm phần trăm hoàn thành, kích thước file, tốc độ file và thời gian còn lại. Đây là một ví dụ khác hiển thị quá trình tải xuống:

![progress](https://github.com/textualize/rich/raw/master/imgs/downloader.gif)

Để tự mình thử, hãy xem [examples/downloader.py](https://github.com/textualize/rich/blob/master/examples/downloader.py) — nó có thể tải nhiều URL cùng lúc trong khi hiển thị tiến trình.

</details>

<details>
<summary>Trạng thái (Status)</summary>

Đối với các tình huống khó tính toán tiến độ, bạn có thể sử dụng phương thức [status](https://rich.readthedocs.io/en/latest/reference/console.html#rich.console.Console.status) để hiển thị hiệu ứng 'spinner' và thông báo. Hiệu ứng này sẽ không ngăn bạn sử dụng console bình thường. Ví dụ:

```python
from time import sleep
from rich.console import Console

console = Console()
tasks = [f"task {n}" for n in range(1, 11)]

with console.status("[bold green]Working on tasks...") as status:
    while tasks:
        task = tasks.pop(0)
        sleep(1)
        console.log(f"{task} complete")
```

Đoạn code trên tạo ra đầu ra sau trong terminal:

![status](https://github.com/textualize/rich/raw/master/imgs/status.gif)

Các hiệu ứng spinner được mượn từ [cli-spinners](https://www.npmjs.com/package/cli-spinners). Bạn có thể chọn một spinner bằng cách chỉ định tham số `spinner`. Chạy lệnh sau để xem các giá trị khả dụng:

```
python -m rich.spinner
```

Lệnh trên tạo ra đầu ra sau trong terminal:

![spinners](https://github.com/textualize/rich/raw/master/imgs/spinners.gif)

</details>

<details>
<summary>Cây (Tree)</summary>

Rich có thể hiển thị một [cây](https://rich.readthedocs.io/en/latest/tree.html) với các đường kẻ hướng dẫn. Cây lý tưởng để hiển thị cấu trúc thư mục hoặc bất kỳ dữ liệu phân cấp nào khác.

Nhãn của cây có thể là văn bản đơn giản hoặc bất kỳ thứ gì Rich có thể hiển thị. Chạy lệnh sau để xem minh họa:

```
python -m rich.tree
```

Kết quả như sau:

![markdown](https://github.com/textualize/rich/raw/master/imgs/tree.png)

Xem ví dụ [tree.py](https://github.com/textualize/rich/blob/master/examples/tree.py) để có script hiển thị cây thư mục bất kỳ, tương tự lệnh `tree` trên Linux.

</details>

<details>
<summary>Cột (Columns)</summary>

Rich có thể hiển thị nội dung theo [cột](https://rich.readthedocs.io/en/latest/columns.html) rất gọn gàng, độ rộng bằng nhau hoặc tối ưu. Chẳng hạn, đoạn code dưới đây mô phỏng lại lệnh `ls` (trên MacOS/Linux) để hiển thị danh sách thư mục theo cột:

```python
import os
import sys

from rich import print
from rich.columns import Columns

directory = os.listdir(sys.argv[1])
print(Columns(directory))
```

Ảnh chụp màn hình dưới đây là đầu ra từ [ví dụ cột](https://github.com/textualize/rich/blob/master/examples/columns.py), hiển thị dữ liệu lấy từ API theo cột:

![columns](https://github.com/textualize/rich/raw/master/imgs/columns.png)

</details>

<details>
<summary>Markdown</summary>

Rich có thể hiển thị [markdown](https://rich.readthedocs.io/en/latest/markdown.html) và thực hiện khá tốt việc chuyển đổi định dạng ra terminal.

Để hiển thị markdown, hãy import lớp `Markdown` và khởi tạo nó với một chuỗi chứa mã markdown. Sau đó in nó ra console. Ví dụ:

```python
from rich.console import Console
from rich.markdown import Markdown

console = Console()
with open("README.md") as readme:
    markdown = Markdown(readme.read())
console.print(markdown)
```

Đoạn code này sẽ tạo ra đầu ra tương tự như sau:

![markdown](https://github.com/textualize/rich/raw/master/imgs/markdown.png)

</details>

<details>
<summary>Syntax Highlighting</summary>

Rich sử dụng thư viện [pygments](https://pygments.org/) để thực hiện [syntax highlighting](https://rich.readthedocs.io/en/latest/syntax.html). Cách sử dụng tương tự như hiển thị markdown; tạo một đối tượng `Syntax` và in nó ra console. Ví dụ:

```python
from rich.console import Console
from rich.syntax import Syntax

my_code = '''
def iter_first_last(values: Iterable[T]) -> Iterable[Tuple[bool, bool, T]]:
    """Iterate and generate a tuple with a flag for first and last value."""
    iter_values = iter(values)
    try:
        previous_value = next(iter_values)
    except StopIteration:
        return
    first = True
    for value in iter_values:
        yield first, False, previous_value
        first = False
        previous_value = value
    yield first, True, previous_value
'''
syntax = Syntax(my_code, "python", theme="monokai", line_numbers=True)
console = Console()
console.print(syntax)
```

Đoạn code trên tạo ra đầu ra như sau:

![syntax](https://github.com/textualize/rich/raw/master/imgs/syntax.png)

</details>

<details>
<summary>Tracebacks</summary>

Rich có thể hiển thị [tracebacks đẹp mắt](https://rich.readthedocs.io/en/latest/traceback.html), dễ đọc và hiển thị nhiều code hơn so với tracebacks Python tiêu chuẩn. Bạn có thể thiết lập Rich làm trình xử lý traceback mặc định để tất cả các ngoại lệ không được bắt đều được hiển thị bởi Rich.

Đây là giao diện trên OSX (tương tự trên Linux):

![traceback](https://github.com/textualize/rich/raw/master/imgs/traceback.png)

</details>

Tất cả các renderable của Rich đều tận dụng [Giao thức Console](https://rich.readthedocs.io/en/latest/protocol.html), bạn cũng có thể dùng nó để tự triển khai nội dung Rich của riêng mình.

# Rich CLI

Xem thêm [Rich CLI](https://github.com/textualize/rich-cli) — một ứng dụng dòng lệnh được hỗ trợ bởi Rich. Tô sáng cú pháp code, hiển thị markdown, hiển thị CSV dưới dạng bảng, v.v., trực tiếp từ command prompt.


![Rich CLI](https://raw.githubusercontent.com/Textualize/rich-cli/main/imgs/rich-cli-splash.jpg)

# Textual

Xem thêm dự án chị em của Rich, [Textual](https://github.com/Textualize/textual), bạn có thể sử dụng để xây dựng các giao diện người dùng phức tạp trong terminal.

![textual-splash](https://github.com/user-attachments/assets/4caeb77e-48c0-4cf7-b14d-c53ded855ffd)

# Toad

[Toad](https://github.com/batrachianai/toad) là một giao diện thống nhất cho lập trình agentic. Được xây dựng với Rich và Textual.

![toad](https://github.com/user-attachments/assets/6678b707-1aeb-420f-99ad-abfcd4356771)