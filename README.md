# Shell

<br/><br/><br/>



## Index
* [sed](#sed)
  * [특정 라인 출력하기](#특정-라인-출력하기)
* [vim](#vim)
  * [tab을 space로 변경하는 방법](#tab을-space로-변경하는-방법)
---

<br/><br/><br/>



## sed

> Usage: sed [OPTION]... {script-only-if-no-other-script} [input-file]...

```shell
$ sed --help

Usage: sed [OPTION]... {script-only-if-no-other-script} [input-file]...

  -n, --quiet, --silent
                 suppress automatic printing of pattern space
      --debug
                 annotate program execution
  -e script, --expression=script
                 add the script to the commands to be executed
  -f script-file, --file=script-file
                 add the contents of script-file to the commands to be executed
  --follow-symlinks
                 follow symlinks when processing in place
  -i[SUFFIX], --in-place[=SUFFIX]
                 edit files in place (makes backup if SUFFIX supplied)
  -b, --binary
                 open files in binary mode (CR+LFs are not processed specially)
  -l N, --line-length=N
                 specify the desired line-wrap length for the `l' command
  --posix
                 disable all GNU extensions.
  -E, -r, --regexp-extended
                 use extended regular expressions in the script
                 (for portability use POSIX -E).
  -s, --separate
                 consider files as separate rather than as a single,
                 continuous long stream.
      --sandbox
                 operate in sandbox mode (disable e/r/w commands).
  -u, --unbuffered
                 load minimal amounts of data from the input files and flush
                 the output buffers more often
  -z, --null-data
                 separate lines by NUL characters
      --help     display this help and exit
      --version  output version information and exit

If no -e, --expression, -f, or --file option is given, then the first
non-option argument is taken as the sed script to interpret.  All
remaining arguments are names of input files; if no input files are
specified, then the standard input is read.

GNU sed home page: <https://www.gnu.org/software/sed/>.
General help using GNU software: <https://www.gnu.org/gethelp/>.
E-mail bug reports to: <bug-sed@gnu.org>.
```

<br/>

### 특정 라인 출력하기

> $ sed -n '< Line-Number >'p < File-Name >  
> $ sed -n '< Regex >'p < File-Name >

```shell
$ env > sed-test

# 한 줄 출력하기
$ sed -n '5p' sed-test
NUMBER_OF_PROCESSORS=8

# 첫 번째 줄부터 5번째 줄 까지 출력
$ sed -n '1, 5p' sed-test
ProgramFiles(x86)=C:\Program Files (x86)
!::=::\
CommonProgramFiles(x86)=C:\Program Files (x86)\Common Files
SHELL=/usr/bin/bash
NUMBER_OF_PROCESSORS=8

# 5번째 줄 부터 끝까지 출력
$ sed -n '75, $p' sed-test
SYSTEMDRIVE=C:
TERM_PROGRAM=mintty
ProgramData=C:\ProgramData
ChocolateyLastPathUpdate=133410395857534822
_=/usr/bin/env
OLDPWD=/c/Users/admin/Desktop

# 정규식에 맞는 라인 출력
$ sed -n '/^OLDPWD=/'p sed-test
OLDPWD=/c/Users/admin/Desktop
```

<br/><br/><br/>



## vim

<br/><br/>



## tab을 space로 변경하는 방법

```shell
# 사용자 홈 디렉토리에서 .vimrc 생성 후 아래 내용 입력
~$ vi .vimrc
set smartindent
set tabstop=4
set expandtab
set shiftwidth=4
...

# 저장 후 종료
: wq



# 프로필 적용
~$ . ~/.vimrc 
```

<br/><br/><br/>



