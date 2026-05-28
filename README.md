# Отчёт к homework для лабораторной работы 01
Скачивание Boost 1.69.0
```bash
$ wget https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz
--2026-05-28 17:01:33--  https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz
Resolving sourceforge.net (sourceforge.net)... 104.18.12.149, 104.18.13.149, 2606:4700::6812:c95, ...
Connecting to sourceforge.net (sourceforge.net)|104.18.12.149|:443... connected.
HTTP request sent, awaiting response... 301 Moved Permanently
Location: https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz/ [following]
--2026-05-28 17:01:34--  https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz/
Reusing existing connection to sourceforge.net:443.
HTTP request sent, awaiting response... 301 Moved Permanently
Location: https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz/download [following]
--2026-05-28 17:01:35--  https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz/download
Reusing existing connection to sourceforge.net:443.
HTTP request sent, awaiting response... 302 Found
Location: https://downloads.sourceforge.net/project/boost/boost/1.69.0/boost_1_69_0.tar.gz?ts=gAAAAABqGEq_dGS_qM5WhyQCuLed6UUnijlnnYzI6F5JXNKiZBhe8DqMdq_NTKKoLumsqIGQw44ZuyB9W-MJbVleF9q6lRYYgw%3D%3D&use_mirror=sf-eu-introserv-2&r= [following]
--2026-05-28 17:01:35--  https://downloads.sourceforge.net/project/boost/boost/1.69.0/boost_1_69_0.tar.gz?ts=gAAAAABqGEq_dGS_qM5WhyQCuLed6UUnijlnnYzI6F5JXNKiZBhe8DqMdq_NTKKoLumsqIGQw44ZuyB9W-MJbVleF9q6lRYYgw%3D%3D&use_mirror=sf-eu-introserv-2&r=
Resolving downloads.sourceforge.net (downloads.sourceforge.net)... 104.18.12.149, 104.18.13.149, 2606:4700::6812:d95, ...
Connecting to downloads.sourceforge.net (downloads.sourceforge.net)|104.18.12.149|:443... connected.
HTTP request sent, awaiting response... 302 Found
Location: https://sf-eu-introserv-2.dl.sourceforge.net/project/boost/boost/1.69.0/boost_1_69_0.tar.gz?viasf=1&fid=0b04351a8c20a7ca [following]
--2026-05-28 17:01:36--  https://sf-eu-introserv-2.dl.sourceforge.net/project/boost/boost/1.69.0/boost_1_69_0.tar.gz?viasf=1&fid=0b04351a8c20a7ca
Resolving sf-eu-introserv-2.dl.sourceforge.net (sf-eu-introserv-2.dl.sourceforge.net)... 51.91.221.175
Connecting to sf-eu-introserv-2.dl.sourceforge.net (sf-eu-introserv-2.dl.sourceforge.net)|51.91.221.175|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 111710205 (107M) [application/x-gzip]
Saving to: ‘boost_1_69_0.tar.gz.1’
```
Разархивирование в текущую папку
```bash
$ tar -xzf boost_1_69_0.tar.gz
```
Количество файлов без учёта вложенных директорий
```bash
$ $ find ./boost_1_69_0 -maxdepth 1 -type f | wc -l
16
```
Количество файлов с учётом вложенных директорий
```bash
$ find ./boost_1_69_0 -type f | wc -l
61837
```
Количество заголовочных (.hpp, .h, .hh), .cpp и остальных файлов
```bash
$ find ./boost_1_69_0 -type f \( -name "*.hpp" -o -name "*.h" -o -name "*.hh" -o -name "*.hxx" \) | wc -l
15208
$ find ./boost_1_69_0 -type f -name "*.cpp" | wc -l
13786
$ total=$(find ./boost_1_69_0 -type f | wc -l)
$ headers=$(find ./boost_1_69_0 -type f \( -name "*.hpp" -o -name "*.h" -o -name "*.hh" -o -name "*.hxx" \) | wc -l)
$ cpp=$(find ./boost_1_69_0 -type f -name "*.cpp" | wc -l)
$ echo "Остальных файлов: $((total - headers - cpp))"
Остальных файлов: 32843
```
Полный путь до any.hpp
```bash
$ find ./boost_1_69_0 -name "any.hpp" -type f
./boost_1_69_0/boost/xpressive/detail/utility/any.hpp
./boost_1_69_0/boost/spirit/home/support/algorithm/any.hpp
./boost_1_69_0/boost/type_erasure/any.hpp
./boost_1_69_0/boost/proto/detail/any.hpp
./boost_1_69_0/boost/hana/fwd/any.hpp
./boost_1_69_0/boost/hana/any.hpp
./boost_1_69_0/boost/fusion/algorithm/query/detail/any.hpp
./boost_1_69_0/boost/fusion/algorithm/query/any.hpp
./boost_1_69_0/boost/fusion/include/any.hpp
./boost_1_69_0/boost/any.hpp
```
Файлы, содержащие последовательность boost::asio
```bash
s$ grep -rl "boost::asio" ./boost_1_69_0
./boost_1_69_0/doc/html/process/reference.html
./boost_1_69_0/doc/html/boost_asio/index.html
./boost_1_69_0/doc/html/boost_asio/overview/ssl.html
./boost_1_69_0/doc/html/boost_asio/overview/posix/stream_descriptor.html
./boost_1_69_0/doc/html/boost_asio/overview/posix/fork.html
./boost_1_69_0/doc/html/boost_asio/overview/core/strands.html
./boost_1_69_0/doc/html/boost_asio/overview/core/line_based.html
./boost_1_69_0/doc/html/boost_asio/overview/core/coroutine.html
./boost_1_69_0/doc/html/boost_asio/overview/core/allocation.html
./boost_1_69_0/doc/html/boost_asio/overview/core/coroutines_ts.html
./boost_1_69_0/doc/html/boost_asio/overview/core/spawn.html
./boost_1_69_0/doc/html/boost_asio/overview/signals.html
./boost_1_69_0/doc/html/boost_asio/overview/cpp2011/move_handlers.html
./boost_1_69_0/doc/html/boost_asio/overview/cpp2011/futures.html
./boost_1_69_0/doc/html/boost_asio/overview/networking/other_protocols.html
./boost_1_69_0/doc/html/boost_asio/overview/networking/protocols.html
./boost_1_69_0/doc/html/boost_asio/examples/cpp11_examples.html
./boost_1_69_0/doc/html/boost_asio/examples/cpp03_examples.html
...

...
./boost_1_69_0/libs/asio/test/buffer.cpp
./boost_1_69_0/libs/asio/test/buffers_iterator.cpp
./boost_1_69_0/libs/asio/test/read_until.cpp
```
Компиляция Boost
```bash
$ sudo apt update
[sudo] password for vlad:
Hit:1 http://deb.debian.org/debian trixie InRelease
Hit:2 http://security.debian.org/debian-security trixie-security InRelease
Hit:3 http://deb.debian.org/debian trixie-updates InRelease
Get:4 https://download.docker.com/linux/debian trixie InRelease [32.5 kB]
Fetched 32.5 kB in 6s (5,772 B/s)
225 packages can be upgraded. Run 'apt list --upgradable' to see them.
$ sudo apt install build-essential g++ python3-dev
build-essential is already the newest version (12.12).
g++ is already the newest version (4:14.2.0-1).
python3-dev is already the newest version (3.13.5-1).
Summary:
  Upgrading: 0, Installing: 0, Removing: 0, Not Upgrading: 225
$ cd boost_1_69_0
$ ./bootstrap.sh --with-libraries=all
Building Boost.Build engine with toolset gcc... tools/build/src/engine/bin.linuxx86_64/b2
Unicode/ICU support for Boost.Regex?... not found.
Backing up existing Boost.Build configuration in project-config.jam.1
Generating Boost.Build configuration in project-config.jam...

Bootstrapping is done. To build, run:

    ./b2

To adjust configuration, edit 'project-config.jam'.
Further information:

   - Command line help:
     ./b2 --help

   - Getting started guide:
     http://www.boost.org/more/getting_started/unix-variants.html

   - Boost.Build documentation:
     http://www.boost.org/build/doc/html/index.html
$ ./b2 -j$(nproc)
Performing configuration checks

    - default address-model    : 64-bit (cached)
    - default architecture     : x86 (cached)

Building the Boost C++ Libraries.


    - C++11 mutex              : yes (cached)
    - lockfree boost::atomic_flag : yes (cached)
    - Boost.Config Feature Check: cxx11_auto_declarations : yes (cached)
    - Boost.Config Feature Check: cxx11_constexpr : yes (cached)
    - Boost.Config Feature Check: cxx11_defaulted_functions : yes (cached)
    - Boost.Config Feature Check: cxx11_final : yes (cached)
    - Boost.Config Feature Check: cxx11_hdr_mutex : yes (cached)
    - Boost.Config Feature Check: cxx11_hdr_tuple : yes (cached)
    - Boost.Config Feature Check: cxx11_lambdas : yes (cached)
...


...
bboost_log_setup.a(clean) for lack of <pbin.v2/libs/log/build/gcc-14.2.0/release/link-static/threadapi-pthread/threading-multi/visibility-hidden>setup/init_from_settings.o...
...skipped <pbin.v2/libs/log/build/gcc-14.2.0/release/link-static/threadapi-pthread/threading-multi/visibility-hidden>libboost_log_setup.a for lack of <pbin.v2/libs/log/build/gcc-14.2.0/release/link-static/threadapi-pthread/threading-multi/visibility-hidden>setup/init_from_settings.o...
...skipped <pstage/lib>libboost_log_setup.a for lack of <pbin.v2/libs/log/build/gcc-14.2.0/release/link-static/threadapi-pthread/threading-multi/visibility-hidden>libboost_log_setup.a...
$ cd ..
```
Перенос всех статических библиотек в ./boost-libs
```bash
$ mkdir -p ./boost-libs
$ find ./boost_1_69_0/stage/lib -name "*.a" -exec cp {} ./boost-libs/ \;
```
Размер каждого файла в ./boost-libs
```bash
$ du -b ./boost-libs/* | sort -n
1308    ./boost-libs/libboost_system.a
1526    ./boost-libs/libboost_exception.a
2450    ./boost-libs/libboost_atomic.a
2694    ./boost-libs/libboost_stacktrace_noop.a
12960   ./boost-libs/libboost_stacktrace_basic.a
18978   ./boost-libs/libboost_stacktrace_backtrace.a
20056   ./boost-libs/libboost_context.a
35284   ./boost-libs/libboost_stacktrace_addr2line.a
52120   ./boost-libs/libboost_timer.a
79070   ./boost-libs/libboost_random.a
151706  ./boost-libs/libboost_date_time.a
151848  ./boost-libs/libboost_container.a
210524  ./boost-libs/libboost_prg_exec_monitor.a
233786  ./boost-libs/libboost_fiber.a
234302  ./boost-libs/libboost_chrono.a
277966  ./boost-libs/libboost_iostreams.a
326562  ./boost-libs/libboost_contract.a
409384  ./boost-libs/libboost_filesystem.a
790730  ./boost-libs/libboost_wserialization.a
843532  ./boost-libs/libboost_graph.a
1192390 ./boost-libs/libboost_serialization.a
1550366 ./boost-libs/libboost_program_options.a
2043618 ./boost-libs/libboost_locale.a
2269102 ./boost-libs/libboost_unit_test_framework.a
2289054 ./boost-libs/libboost_test_exec_monitor.a
2758078 ./boost-libs/libboost_regex.a
4638498 ./boost-libs/libboost_wave.a
```
Топ‑10 самых тяжёлых файлов
```bash
$ du -b ./boost-libs/* | sort -nr | head -10
4638498 ./boost-libs/libboost_wave.a
2758078 ./boost-libs/libboost_regex.a
2289054 ./boost-libs/libboost_test_exec_monitor.a
2269102 ./boost-libs/libboost_unit_test_framework.a
2043618 ./boost-libs/libboost_locale.a
1550366 ./boost-libs/libboost_program_options.a
1192390 ./boost-libs/libboost_serialization.a
843532  ./boost-libs/libboost_graph.a
790730  ./boost-libs/libboost_wserialization.a
409384  ./boost-libs/libboost_filesystem.a
```
