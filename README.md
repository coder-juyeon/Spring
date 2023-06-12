# 코리아 IT 아카데미 국비과정
<a name="readme-top"></a>
## spring 

### Day 01

* #### Framework
```
	뼈대나 근간을 이루는 코드들의 묶음.
	라이브러리나, 개발자가 작성해놓은 코드파일을 의미하며
	API란, 여러 라이브러리가 모여있는 패키지(JAR)를 의미한다.
	프레임워크란, API가 굉장히 많이 모여저서 덩치가 커져있는 것을 의미한다.
	개발자는 각 개개인의 능력차이가 큰 직종이고, 개발자 구성에 따라 프로젝트 결과 역시
	큰 차이를 낳는다. 이런 상황을 극복하기 위한 코드의 결과물이 바로 프레임워크이다.
	프로그램의 기본 흐름이나 구조를 정하고 모든 팀원이 이 구조에 자신의 코드를 추가하는 방식으로
	개발하게 된다.
```
  
* #### Framework의 장점
```
	개발에 필요한 구조를 이미 코드로 만들어 놓았기 때문에, 실력이 부족한 개발자라 하더라도
	반쯤 완성된 상태에서 필요한 부분을 조립하는 형태의 개발이 가능하다.
	회사 입장에서는 프레임워크를 사용하면 일정한 품질이 보장되는 결과물을 얻을 수 있고,
	개발자 입장에서는 완성된 구조에 자신이 맡은 서비스에 대한 코드를 개발해서 넣기 때문에
	개발 시간을 단축할 수 있다.
```

* #### Spring Framework
```
	경량 프레임워크, 
	예전 프레임워크는 다양한 경우를 처리하기 위해 여러 기능들을 넣다보니,
	하나의 기능을 위해서 아주 많은 구조가 필요했다. 기술이 너무나 복잡하고 방대했기 때문에,
	전체를 이해하고 개발하기에는 어려움이 많았다. 그래서 Spring Framework가 등장했고,
	특정 기능을 위주로 간단한 JAR파일 등을 선택하여 모든 개발이 가능하도록 구성되어 있다.
```

* #### Spring Framework의 장점
```
	- 프로젝트 전체 구조를 설계할 때 유용하다(빠른 속도로  서버 제작 가능)
	- 다른 프레임워크들의 포용, 여러 프레임워크를 혼용해서 사용 가능하며 이를 접착성이 좋다고 한다.
	- 개발 생산성과 개발도구의 지원
```

* #### Spring Boot
```
	Spring Framework를 사용함에 있어서 초기 설정 및 필요한 라이브러리에 대한 설정의 어려움이 많으며,
	시간이 너무 오래 걸리 때문에 자동 설정(AutoConfiguration)과 개발에 필요한 모든 것을 관리해주는
	스프링 부트를 선호한다. 각 코어 및 라이브러리의 버전들도 맞추어야 하지만 스프링 부트를 사용하면
	이러한 복잡성을 해결하기에도 좋다.
```

* #### Spring Framework의 특징
```
	- POJO 기반의 구성
	- DI를 통한 객체간의 관계 구성
	- AOP 지원
	- Transaction 관리
	- 편리한 MVC 구조
	- WAS에 종속적이지 않은 개발 환경
```

* #### ▶ POJO 기반의 구성
```
	오래된 방식의 간단한 자바 객체라는 의미이며, JAVA코드에서 일반적으로 객체를 구성하는 방식을
	Spring Framework에서 그대로 사용할 수 있다는 의미이다.
```

* #### ▶ 의존성 주입(DI)을 통한 객체간의 관계 구성
```
	의존성(Dependency)이란 하나의 객체가 다른 객체 없이 제대로 된 역할을 할 수 없다는 것을 의미한다.
	예를 들어 A객체가 B객체 없이 동작이 불가능한 상황을 "A가 B에 의존적이다"라고 표현한다.
	하지만 직접 A필드에 B객체를 선언하면 결합도가 단단해지기 때문에 유연성이 떨어진다.

	주입(Injection)은 외부에서 내부로 밀어 넣는 것을 의미한다.
	필요한 객체를 외부에서 밀어 넣어 유연성을 높이고 결합도를 느슨하게 해준다.
	주입을 받는 입장에서는 어떤 객체인지 신경 쓸 필요가 없고 어떤 객체에 의존하든 자신의 역할은 변하지 않는다.

   	***의존성
   	A →→→→→→→→→→→→→ B
   	A객체에서 B객체를 필드로 직접 생성

	***의존성 주입
	A ↔↔↔↔↔ ? ↔↔↔↔↔ B
	A는 B가 필요하다고 신호를 보내고, ?가 B객체를 외부에서 생성하여 주입하게 된다.
	Spring Framework에서는 ApplicationContext가 ?이며,
	필요한 객체들을 생성 및 주입해주는 역할을 한다. 따라서 개발자들은 기존의 프로그래밍과는 달리
	객체와 객체를 분리해서 생성하고, 이러한 객체를 엮는 wiring 작업의 형태로 개발하게 된다.

	ApplicationContext가 관리하는 객체들을 빈(Bean)이라 부르고,
	빈과 빈 사이의 의존관계를 처리하는 방식으로는 XML, 어노테이션, JAVA 방식이 있다.
```

* #### ▶ AOP의 지원
```
	관점 지향 프로그래밍.
	좋은 개발 환경에서는 개발자가 비지니스 로직에만 집중할 수 있게 한다.
	Spring Framework는 반복적인 코드를 제거해줌으로써 핵심 비지니스 로직에만
	집중할 수 있는 방법을 제공한다.
	보안이나 로그, 트랜잭션, 예외처리와 같이 비지니스 로직은 아니지만,
	반드시 처리가 필요한 부분을 주변 로직(횡단 관심사)라고 하고, 개발해야할 서비스는 메인 로직(종단 관심사)라고 한다.
	Spring Framwork는 이러한 횡단 관심사를 분리해서 설계하는 것이 가능하고, 횡단 관심사를 모듈로
	분리하는 프로그래밍을 AOP라고 한다.
	핵심 비지니스 로직에만 집중하여 코드 개발이 가능해지고, 각 프로젝트마다 다른 관심사 적용 시 코드 수정을
	최소화 할 수 있으며, 원하는 관심사의 유지보수가 수월한 코드로 구성이 가능해진다.
	※ 비지니스 로직: 서비스를 개발하기 위한 소스코드 및 알고리즘
```

<img width="500" src ="https://github.com/coder-juyeon/Spring/assets/122768623/1ee3c14b-b6dc-432b-a8aa-4387d8c36ab8">
<img width="500" src ="https://github.com/coder-juyeon/Spring/assets/122768623/2cea959c-d094-4328-aa52-97b58ce4e58b">


* #### ▶ 트랜젝션의 지원
```
	트랜젝션 작업의 최소 단위
	DB 작업 시 트랜잭션을 매번 상황에 맞게 코드로 작성하지 않고, 어노테이션이나
	XML로 트랜잭션을 쉽게 관리할 수 있다.
```

* #### ▶ 단위 테스트
```
	전체 Application을 실행하지 않아도 기능별 단위 테스트가 용이하기 때문에
	버그를 줄이고 개발 시간을 단축할 수 있다.
```

* #### 프로젝트 기본 경로
```
	1) src/main/java		: 서버단 JAVA 파일
	2) src/test/java		: 단위 테스트 JAVA 파일
	3) src/main/resources		: 설정 파일 및 뷰단 (/만 쳐도 알아서 resources까지)
	4) src/main/resources/static	: css, js, image 등 정적 파일 경로
	5) src/main/resources/templates : html 파일 경로
	6) build.gradel			: 라이브러리 관리
	7) application.yml		: Spring의 모든 설정 야멜
```
    
-------------------------------------------------------------------------------------
### Day 02

* #### 필드주입
```
	사용 방법이 매우 편하다는 장점이 있다.
	주입된 객체를 불변(immutable)상태로 만들 수 없기 때문에 외부에서 수정될 위험이 있다.
	순환 참조 발생시 Application 동작 시점과 Runtime 시점 중 필드주입은 RunTime 시점에 해당하기 때문에
	메모리에 계속 할당되고 StackOverFlow가 발생했다. 하지만 2.6버전 이상부터는 Application 동작 시점에서 잡힌다.
	단위테스트에서는 필드주입만 사용
	생성자 -> 필드주입 -> 세터주입
```
-------------------------------------------------------------------------------------
### Day 03

* #### Spring MVC(Front-Controller Pattern)
```
	MVC (Model-View-Controller) 아키텍처 패턴을 기반으로 하는 웹 개발
	
				HandlerMaping
	REQUEST		  ①	      ②↕	   ③		       ④
			  ↔	DispatcherServlet   ↔  HandlerAdapter   ↔  Controller
	RESPONSE	  ⑦	⑥↕	     ⑤↕
			View	ViewResolver
			   ↕
			HTML 및 기타
```

* #### Spring MVC 패턴의 특징
```
	- HttpServletRequest, HttpServletResponse를 거의 사용할 필요 없이 구현 가능
	- 다양한 타입의 파라미터 처리, 다양한 타입의 리턴 타입 사용 가능
	- Get 방식, POST 방식 등 전송 방식에 대한 처리를 어노테이션으로 처리 가능
	- 상속/인터페이스 방식 대신 어노테이션으로만 설정 가능
```

* #### 타임리프
```
	'템플릿 엔진'의 일종. html 태그에 속성을 추가해 페이지에 동적으로 값을 추가하거나 처리할 수 있음
	▶ html 태그에 속성 추가
	<html lang="en" xmlns:th="http://www.thymeleaf.org">
```

* #### annotation 사용법
```
annotation
	클래스와 메서드에 추가하여 다양한 기능을 부여하는 역할
	Spring Framework는 해당 클래스가 어떤 역할인지 정함
	Bean을 주입
	자동으로 getter나 setter를 생성
	특별한 의미를 부여하거나 기능 부여
	
	1. Bean 등록
	2. 의존성 주입(Dependency Injection)
	3.트랜잭션 관리
	4. MVC 웹 애플리케이션 개발
```

* #### ▶ Bean등록
```
@Bean
	Bean은 스프링 프레임워크에서 관리되는 객체를 의미
	@Bean Annotation은 개발자가 제어가 불가능한 외부 라이브러리와 같은 것들을 Bean으로 만들 때 사용
	스프링 컨테이너에 Bean으로 등록하기 위해
	예) @Component, @Service, @Repository, @Controller
```

* #### ▶ 의존성 주입(Dependency Injection)
```
	객체 간의 관계를 자동으로 설정하기 위해
	@Autowired
```

* #### ▶ 트랜잭션 관리
```
트랜잭션 
	데이터베이스의 상태를 변경하는 일련의 작업을 하나의 논리적인 단위로 묶은 것.
	이 작업들은 모두 성공적으로 수행되어야 하며, 그렇지 않을 경우 이전 상태로 롤백
	@Transactional
```

* #### ▶ MVC 웹 애플리케이션 개발
```
	스프링 MVC를 사용하여 웹 애플리케이션을 개발할 때 어노테이션을 활용
	@Controller, @RequestMapping, @RequestParam, @ResponseBody 등의 어노테이션을 사용하여 요청을 처리하고 응답을 생성
```

* #### @Controller
```
@Controller
	Controller의 역할을 수행 한다고 명시(해당 클래스를 Controller로 사용한다고 Spring FrameWork에 알린다.)

   	필요한 비즈니스 로직을 호출하여 전달할 모델(Model)과 이동할 뷰(View) 정보를 DispatherServlet에 반환 한다.

 	- Bean으로 등록

 	- @Component의 구체화 된 어노테이션
	frontController처럼 쓸 수 있다.
```
<img width="900" src="https://github.com/coder-juyeon/Spring/assets/122768623/efc551ae-b8a1-42c4-973d-2f2641e0103c">


* #### @RequestMapping
```
	class와 Method를 같이 쓸때
	예) @RequestMapping("/ex/")
	공통적인 url을 설정해줌
```

* #### @ModelAttribute
```
	@ModelAttribute("name")String name
	html에서 jstl을 쓰기 위해
	매개변수에 주기
	예)
	@GetMapping("ex04")
	    public void ex04(String name, Model model) {
		model.addAttribute("name", name);
		log.info(name);
	}

	= (위와 아래가 같음)

	@GetMapping("ex04")
	    public void ex04(@ModelAttribute("name")String name) {
		log.info(name);
	}
```

* #### @RequestParam
```
@RequestParam
	1대1 매핑
	화면에서 받을 파라미터 이름과 자바에서 받을 매개변수 이름이 다를때 사용한다.
	예) 파라미터는 address(화면) 매개변수는 city면
	    @RequestParam("address") String city
    
@RequestParam, @ModelAttribute의 차이점
	modelAttribute은 파라미터를 객체 타입으로 받을 수 있지만
	RequestParam은 1대1 매핑으로 파라미터에 데이터 하나만 가져올 수 있다.

	예)
	public class UserSearchForm() {
		private int id;
		private String name;
		private String email;
		private String phone;
	}

	@ModelAttribute의 경우
	public String getTestPage(@ModelAttribute UserSearchForm userSearchForm){
	}

	@RequestParam의 경우
	public String getTestPage(@RequestParam int id, @RequestParam String name, @RequestParam String email,@RequestParam String phone){
	}
```

-------------------------------------------------------------------------------------
### Day 05

* #### Assertions.asertThat()
```
 	친절한 오류 설명 및 빠른 단위 테스트 가능
 	assertj꺼 쓰기
```

-------------------------------------------------------------------------------------
### Day 06

* #### REST
```
	- Representational State Transfer
	- 자원, 행위, 표현으로 구성되어 있다.
	- 언제, 어디서든 누구든 서버에 요청을 보낼 때 URI만으로도 데이터 및 CRUD의 상태를 이해할 수 있도록 설계하는 규칙.
	- HTTP에 존재하는 모든 자원에 고유한 URI를 부여하여 활용하는 것으로 자원을 정의하고 자원에 대한 주소를 지정하는 방법론
	- JSON 혹은 XML을 통해 데이터를 주고 받는 것이 일반적 
	- 네트워크 상에서 Client와 Server사이의 통신 방식 중 하나
	- HTTP URL을 통해 자원을 명시하고 HTTP Method(POST, GET, PUT, DELETE)를 통해 해당 자원에 대한 CRUD Operation을 적용하는 것을 의미

	* CRUD Operation
	Create : 생성(POST)
	Read : 조회(GET)
	Update : 수정(PUT)
	Delete : 삭제(DELETE)

	* RESTful
	-REST 방식을 따른 시스템

	* RESTful API
	-설계 방식이 모두 REST 규칙에 의해 작성된 API.
```

* #### 3-tier
```
	3-tier
	   스프링 프로젝트는 3-tier 방식으로 구성한다.

	   ▶ Presentation Tier - 화면 계층
	      화면에 보여주는 기술을 사용하는 영역

	   ▶ Buisiness Tier - 비지니스 계층, 로직 계층
	      순수한 비지니스 로직을 담고 있는 영역

	   ▶ Persistence Tier - 영속 계층, 데이터 계층
	      데이터를 어떤 방식으로 보관하고, 사용하는 가에 대한 설계가 들어가는 영역

	3-tier의 목적
		각 영역은 독립적으로 설계되어 
		나중에 특정 기술이 변하더라도 필요한 부분을 전자제품의 부품처럼 쉽게 교환할 수 있게 하자는 방식이다.

	3-tier의 구조
		Presentation ↔ Business ↔ Persistence ↔ DBMS
				↑      ↑         ↑
			Controller   Service       Mapper
```
* #### REST URI 규칙
```
	1. 소문자로 작성한다.
		대문자로 작성시 문제가 발생할 수 있기 때문에 소문자로 작성한다.

	2. 언더바 대신 하이픈을 사용한다.
		가독성을 높이기 위해서 하이픈으로 구분하는 것이 좋다.

	3. URI 마지막은 슬래시를 작성하지 않는다.	
		마지막에 작성하는 슬래시는 의미가 없다.		

	4. 계층 관계 표현 시 슬래시 구분자로 사용한다.
		계층 관계(포함 관계)에서는 슬래시로 구분해준다.

	5. 동사는 작성하면 안된다.
		행위는 URI로 표현하지 않고 HTTP METHOD를 통해 전달한다.
	
	6. 파일 확장자는 포함시키지 않는다.
		파일 확장자는 URI로 표현하지 않고 Header의 Content-Type을 사용하여
		body의 내용을 처리하도록 설계한다.

	7. 데이터를 대표할 때에는 명사를 사용하지만, 상태를 대표할 때에는 동사를 허용한다.
		http://www.app.com/writing (X)
		http://www.app.com/write (O)		

	8. URI에 사용되는 영어단어는 복수로 작성한다.

```

-------------------------------------------------------------------------------------
### Day 07

* #### 제목
```
내
용
입
력
```
* #### 제목
```
내
용
입
력
```


### Built With

This section should list any major frameworks/libraries used to bootstrap your project. Leave any add-ons/plugins for the acknowledgements section. Here are a few examples.

* [![Next][Next.js]][Next-url]
* [![React][React.js]][React-url]
* [![Vue][Vue.js]][Vue-url]
* [![Angular][Angular.io]][Angular-url]
* [![Svelte][Svelte.dev]][Svelte-url]
* [![Laravel][Laravel.com]][Laravel-url]
* [![Bootstrap][Bootstrap.com]][Bootstrap-url]
* [![JQuery][JQuery.com]][JQuery-url]

<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- GETTING STARTED -->
## Getting Started

This is an example of how you may give instructions on setting up your project locally.
To get a local copy up and running follow these simple example steps.

### Prerequisites

This is an example of how to list things you need to use the software and how to install them.
* npm
  ```sh
  npm install npm@latest -g
  ```

### Installation

_Below is an example of how you can instruct your audience on installing and setting up your app. This template doesn't rely on any external dependencies or services._

1. Get a free API Key at [https://example.com](https://example.com)
2. Clone the repo
   ```sh
   git clone https://github.com/your_username_/Project-Name.git
   ```
3. Install NPM packages
   ```sh
   npm install
   ```
4. Enter your API in `config.js`
   ```js
   const API_KEY = 'ENTER YOUR API';
   ```

<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- USAGE EXAMPLES -->
## Usage

Use this space to show useful examples of how a project can be used. Additional screenshots, code examples and demos work well in this space. You may also link to more resources.

_For more examples, please refer to the [Documentation](https://example.com)_

<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- ROADMAP -->
## Roadmap

- [x] Add Changelog
- [x] Add back to top links
- [ ] Add Additional Templates w/ Examples
- [ ] Add "components" document to easily copy & paste sections of the readme
- [ ] Multi-language Support
    - [ ] Chinese
    - [ ] Spanish

See the [open issues](https://github.com/othneildrew/Best-README-Template/issues) for a full list of proposed features (and known issues).

<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- CONTRIBUTING -->
## Contributing

Contributions are what make the open source community such an amazing place to learn, inspire, and create. Any contributions you make are **greatly appreciated**.

If you have a suggestion that would make this better, please fork the repo and create a pull request. You can also simply open an issue with the tag "enhancement".
Don't forget to give the project a star! Thanks again!

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- LICENSE -->
## License

Distributed under the MIT License. See `LICENSE.txt` for more information.

<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- CONTACT -->
## Contact

Your Name - [@your_twitter](https://twitter.com/your_username) - email@example.com

Project Link: [https://github.com/your_username/repo_name](https://github.com/your_username/repo_name)

<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- ACKNOWLEDGMENTS -->
## Acknowledgments

Use this space to list resources you find helpful and would like to give credit to. I've included a few of my favorites to kick things off!

* [Choose an Open Source License](https://choosealicense.com)
* [GitHub Emoji Cheat Sheet](https://www.webpagefx.com/tools/emoji-cheat-sheet)
* [Malven's Flexbox Cheatsheet](https://flexbox.malven.co/)
* [Malven's Grid Cheatsheet](https://grid.malven.co/)
* [Img Shields](https://shields.io)
* [GitHub Pages](https://pages.github.com)
* [Font Awesome](https://fontawesome.com)
* [React Icons](https://react-icons.github.io/react-icons/search)

<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
[contributors-shield]: https://img.shields.io/github/contributors/othneildrew/Best-README-Template.svg?style=for-the-badge
[contributors-url]: https://github.com/othneildrew/Best-README-Template/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/othneildrew/Best-README-Template.svg?style=for-the-badge
[forks-url]: https://github.com/othneildrew/Best-README-Template/network/members
[stars-shield]: https://img.shields.io/github/stars/othneildrew/Best-README-Template.svg?style=for-the-badge
[stars-url]: https://github.com/othneildrew/Best-README-Template/stargazers
[issues-shield]: https://img.shields.io/github/issues/othneildrew/Best-README-Template.svg?style=for-the-badge
[issues-url]: https://github.com/othneildrew/Best-README-Template/issues
[license-shield]: https://img.shields.io/github/license/othneildrew/Best-README-Template.svg?style=for-the-badge
[license-url]: https://github.com/othneildrew/Best-README-Template/blob/master/LICENSE.txt
[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=for-the-badge&logo=linkedin&colorB=555
[linkedin-url]: https://linkedin.com/in/othneildrew
[product-screenshot]: images/screenshot.png
[Next.js]: https://img.shields.io/badge/next.js-000000?style=for-the-badge&logo=nextdotjs&logoColor=white
[Next-url]: https://nextjs.org/
[React.js]: https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB
[React-url]: https://reactjs.org/
[Vue.js]: https://img.shields.io/badge/Vue.js-35495E?style=for-the-badge&logo=vuedotjs&logoColor=4FC08D
[Vue-url]: https://vuejs.org/
[Angular.io]: https://img.shields.io/badge/Angular-DD0031?style=for-the-badge&logo=angular&logoColor=white
[Angular-url]: https://angular.io/
[Svelte.dev]: https://img.shields.io/badge/Svelte-4A4A55?style=for-the-badge&logo=svelte&logoColor=FF3E00
[Svelte-url]: https://svelte.dev/
[Laravel.com]: https://img.shields.io/badge/Laravel-FF2D20?style=for-the-badge&logo=laravel&logoColor=white
[Laravel-url]: https://laravel.com
[Bootstrap.com]: https://img.shields.io/badge/Bootstrap-563D7C?style=for-the-badge&logo=bootstrap&logoColor=white
[Bootstrap-url]: https://getbootstrap.com
[JQuery.com]: https://img.shields.io/badge/jQuery-0769AD?style=for-the-badge&logo=jquery&logoColor=white
[JQuery-url]: https://jquery.com 
