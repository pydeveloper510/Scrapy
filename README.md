# Scrapy
Scrapy pattern

## settings.py
AUTOTHROTTLE_ENABLED = True
HTTPCACHE_ENABLED = True
FEED_FORMAT = "csv"
FEED_URI = "res.csv"

 Scrapy 프로젝트에서 구현 한 bot 이름 (프로젝트 이름이라고도 함)
BOT_NAME = 'test'

SPIDER_MODULES = ['test.spiders']
NEWSPIDER_MODULE = 'test.spiders'


# User-agent 설정
USER_AGENT = 'test'

# 타켓 사이트 Robots.txt 준수 여부
# True 활성화하면 Scrapy는 robots.txt 정책을 준수
ROBOTSTXT_OBEY = False

# 병렬 처리. 주석처리면 기본 16으로 설정됨
# Scrapy 다운로더가 수행 할 최대 동시 (즉, 동시) 요청 수
CONCURRENT_REQUESTS = 32

# 다운로드 딜레이
# 웹 사이트에서 연속 페이지를 다운로드하기 전에 다운로더가 기다려야하는 시간 (초)
DOWNLOAD_DELAY = 2

# 웹 사이트 도메인 동시 병렬 처리 개수
CONCURRENT_REQUESTS_PER_DOMAIN = 16

# 특정 웹 사이트 IP 주소 병렬 처리 개수
CONCURRENT_REQUESTS_PER_IP = 16

# 쿠키 활성화 여부
COOKIES_ENABLED = True

# Telnet Console 활성화 여부
TELNETCONSOLE_ENABLED = False

# 기본 Request 헤더
DEFAULT_REQUEST_HEADERS = {
   'Referer': 'https://news.daum.net/',
}

# 미들웨어 사용 여부
SPIDER_MIDDLEWARES = {
   'test.middlewares.TestSpiderMiddleware': 543,
}

# 특정 다운로드 미들웨어 사용
DOWNLOADER_MIDDLEWARES = {
    'test.middlewares.TestDownloaderMiddleware': 543,
}

# 프로젝트에서 활성화 된 확장과 그 순서를 포함하는 dict
EXTENSIONS = {
    'scrapy.extensions.telnet.TelnetConsole': None,
}

파이프라인 설정
ITEM_PIPELINES = {
    'test.pipelines.TestPipeline': 300,
}

# 캐시를 사용하면 동일하게 여러 번 요청 시 서버 사이드에 부하 절감 가능(변동사항 없을 경우)
# 캐시 사용 여부
HTTPCACHE_ENABLED = False
# 캐시 유효 기간
HTTPCACHE_EXPIRATION_SECS = 30
# 캐시 저장 경로
HTTPCACHE_DIR = 'httpcache'
# 응답 거부 캐시
HTTPCACHE_IGNORE_HTTP_CODES = []
HTTPCACHE_STORAGE = 'scrapy.extensions.httpcache.FilesystemCacheStorage'

# 한글 쓰기(출력 인코딩)
FEED_EXPORT_ENCODING = 'utf-8'

# 오류 처리
# 자동 재시도 설정
RETRY_ENABLED = True

# 재시도 횟수 최대값
RETRY_TIMES = 2

# 재시도 대상 HTTP 코드
RETRY_HTTP_CODES = [500, 502, 503, 504, 408]

# 오류 무시 HTTP 상태 코드
HTTPERROR_ALLOWED_CODES = [404]

# 모든 상태 코드 오류 무시 (사용 비추천)
HTTPERROR_ALLOW_ALL = False
