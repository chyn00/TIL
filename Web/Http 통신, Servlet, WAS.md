# URL
 * A class, B class, C class
# Client Vs Server

# IP Vs Protocol
 * IP : 서버의 주소
 * Protocol : 서버 프로그램의 주소

# HTTP란?
 * HTTP(HyperText Transfer Protocol)의 약자로
 * 하이퍼 텍스트를 주고받는 규약(프로토콜)이다.
 * 하이퍼 텍스트 종류는 HTML / JSON / XML등이 있다.
 * Server side에서는 json을 주고 받는다고 생각되지만, 사실 잘 생각해보면 우리가 사용하는 도메인도 모두 Http 요청으로 되어있다.

# 정적자원 vs 동적자원
 * 정적 자원 : 고정되어있는 html
 * 동적 자원 : 값(쿼리 파람 등)에 따라 결과가 달라지는 JS, JSP(특히 JSP에서의 스크립트 구문) 등이 있다.

# 웹프로그래밍이란?
 * 웹서버가 웹 브라우저에 응답으로 전송할 데이터를 생성해주는 프로그램을 작성하는 것

# JSP
 * Java server programming이며, json/xml보다는 html응답을 중점으로 하는 자바 프로그래밍이다.
 * 주된 목적은 Html 응답.

# WAS
 * HTML은 정적 파일만을 보내주는 반면, 
 * WAS : 동적으로 DB도 연결해주고
 * WAS는 사실 영어권에서는 Application Server라고 불린다.

# JSP에서는 기본 객체를 사용하고 있다.
  * request, response, session, application, page 등


# 톰캣은 자바로 구현되어있고, 자바의 서블릿은 네트워크 통신을 할 수 있는 객체로 구현되어있다.
 * 결국 객체의 네트워크 통신을 관리하는 것이 톰캣이다.
 * 생각해보면 스프링컨테이너는 스프링의 빈 주기들을 관리해주기 위함이기 때문에, 서버는 톰캣에 띄워진것이 맞다고 보면된다.


1. 스프링은 그 자체로 서버를 띄울 수 있는가? 정답 : 아니다.
2. 서버를 띄우는 주체는 누구인가? WAS(내부는 자바)

# WAS의 위치
스프링 or 부트 > 스프링 웹 (의존성 jar) > WAS(tomcat 등)

# 사실 스프링이라는 넓은 범위안에서, 스프링 웹이라는 dependency 안에 WAS(Tomcat 등)이 내장되어있는 것임.

# 참고로 톰캣은 자바로 구현되어있고, 톰캣 내부에 servlet이라는 것도 자바 객체들로 구현되어있음.

# Servlet Life Cycle
 * Servlet은 최초 Request시 init()으로 초기화된 객체가 생성되고,
 * 이후부터는 Service Method를 사용한다.(Thread 마다 1개씩 생성)
 * Destroy또한 마찬가지로 최종 1회 작동(Servlet Container가 제어.)
 * https://www.tutorialspoint.com/servlets/servlets-life-cycle.htm 참조

정리를 위한 OX
스프링은 무조건 tomcat을 포함한다.(X)
스프링 부트는 무조건 tomcat을 포함한다.(X)
tomcat은 자바로 구현된 http 통신을 위한 자바 객체로 이루어진 프로그램이다.(O)
servlet container를 포함한 WAS와 자바만으로 서버의 요청과 응답을 만드는 것이 가능하다.(O)
스프링은 웹개발을 쉽게 만들어주는 도구이이지만, 서버를 띄우는 도구는 아니다.(O)
tomcat만이 WAS는 아니다. jetty라는 것도 존재한다.(O)
WAS는 Servlet 컨테이너를 포함하고 있으나, 그 자체는 아니다.  HTTP 통신만이 아닌, DB Connection과 같은 부분도 감당한다.(O)

결국 자바 HTTP 웹 환경에서 서버를 띄우고, 클라이언트의 요청, 응답을 관리하는 프로그램을 넓은 범위에서 WAS라고 하며, 내부는 Servlet Container가 자바로 구현되어있다.
그래서, Servlet에서 규약(헤더, param, body 등)을 활용하여, 웹의 요청들을 자바에서 처리하도록 돕는 것이다.

물론 원론적인 통신외에, 추가 처리가 필요한 부분은 스프링에서 요청에 대해 후처리, 전처리(filter, Interceptor)등을 관리하기는 한다.
하지만 자바 웹 통신의 더 작은 단위는 결국 WAS와 Servlet이다.
