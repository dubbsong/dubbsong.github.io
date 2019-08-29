---
layout: post
title: "인터넷은 어떻게 동작하는가?"
categories: dev
tags: basic
---

###### [MDN web docs](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/How_does_the_Internet_work) 번역

<br>

## Summary

- The `Internet` is the backbone of the Web, the technical infrastructure that makes the Web possible.
  - `Internet`은 웹(Web)의 중추이다.
  - 웹을 가능하게 하는 기술 인프라(기반 시설)이다.
- At its most basic, the Internet is a large network of computers which communicate all together.
  - 가장 기본적으로, 인터넷은 모두 함께 통신하는 대규모 컴퓨터 네트워크이다.
- [The history of the Internet is somewhat obscure](https://en.wikipedia.org/wiki/Internet#History).
  - [인터넷의 역사는 다소 모호하다](https://en.wikipedia.org/wiki/Internet#History).
- It began in the 1960s as a US-army-funded research project, then evolved into a public infrastructure in the 1980s with the support of many public universities and private companies.
  - 인터넷은 1960년 대 미군이 기금을 조성한 연구 프로젝트로 시작되었다.
  - 그리고 1980년 대 많은 국립 대학과 사기업의 지원으로 인해 공공 인프라로 발전되었다.
- The various technologies that support the Internet have evolved over time, but the way it works hasn't changed that much: Internet is a way to connect computers all together and ensure that, whatever happens, they find a way to stay connected.
  - 인터넷을 지원하는 다양한 기술들은 시간이 지남에 따라 발전했지만, 그 동작 방식은 크게 변하지 않았다.
  - 인터넷은 컴퓨터를 모두 연결하고, 무슨 일이 있어도 연결 상태를 유지할 수 있는 방법을 찾는 방법이다.

<br>

<br>

## Deeper dive

###### 깊게 들어가기

<br>

###### A simple network (단순한 네트워크)

- When two computers need to communicate, you have to link them, either physically (usually with an [Ethernet cable](https://en.wikipedia.org/wiki/Ethernet_crossover_cable)) or wirelessly (for example with [WiFi](https://en.wikipedia.org/wiki/WiFi) or [Bluetooth](https://en.wikipedia.org/wiki/Bluetooth) systems).
  - 두 대의 컴퓨터가 통신해야 할 때, 물리적([이더넷 케이블](https://en.wikipedia.org/wiki/Ethernet_crossover_cable)) 또는 무선([와이파이](https://en.wikipedia.org/wiki/WiFi) 또는 [블루투스](https://en.wikipedia.org/wiki/Bluetooth))으로 연결해야 한다.
- All modern computers can sustain any of those connections.
  - 모든 최신 컴퓨터는 이러한 연결을 유지할 수 있다.

<br>

> **Note:**
>
> For the rest of this article, we will only talk about physical cables, but wireless networks work the same.
>
> 이 글의 나머지 부분에서는 물리적 케이블에 대해서만 이야기하지만, 무선 네트워크도 동일하게 동작한다.

<br>![img](/assets/img/mdn-internet-01.png)

<br>

- Such a network is not limited to two computers.
  - 이러한 네트워크는 두 대의 컴퓨터로 제한되지 않는다.
- You can connect as many computers as you wish.
  - 원하는 만큼의 컴퓨터를 연결할 수 있다.
- But it gets complicated quickly.
  - 하지만 연결할수록 빠르게 복잡해진다.

<br>

- If you're trying to connect, say, ten computers, you need 45 cables, with nine plugs per computer!
  - 예를 들어 10 대의 컴퓨터를 연결하려는 경우, 컴퓨터 당 9개의 플러그가 있는 45개의 케이블이 필요하다.

![img](/assets/img/mdn-internet-02.png)

<br>

- To solve this problem, each computer on a network is connected to a special tiny computer called a `router`.
  - 이 문제를 해결하기 위해, 네트워크의 각 컴퓨터는 `라우터(router)`라는 특수한 소형 컴퓨터에 연결된다.
- This router has only one job: like a signaler at a railway station, it makes sure that a message sent from a given computer arrives at the right destination computer.
  - 이 라우터는 단 하나의 작업만 한다.
  - 철도역의 신호수(신호원)처럼, 지정된 컴퓨터에서 보낸 메시지가 올바른 대상 컴퓨터에 도착하는지 확인한다.
- To send a message to computer B, computer A must send the message to the router, which in turn forwards the message to computer B and makes sure the message is not delivered to computer C.
  - B 컴퓨터로 메시지를 보내기 위해, A 컴퓨터가 라우터로 메시지를 보내야 한다.
  - 라우터는 메시지를 B 컴퓨터로 전달한다.
  - 메시지가 C 컴퓨터로 전달되지 않도록 해야 한다.

<br>

- Once we add a router to the system, our network of 10 computers only requires 10 cables: a single plug for each computer and a router with 10 plugs.
  - 시스템에 라우터를 추가하면, 10 대의 컴퓨터 네트워크에는 10개의 케이블만 필요하다.
  - 각 컴퓨터마다 하나의 플러그와, 10개의 플러그가 있는 라우터이다.

![img](/assets/img/mdn-internet-03.png)

<br>

<br>

###### A network of network (네트워크의 네트워크)

- So far so good.
  - 지금까지 그런대로 괜찮았다.
- But what about connecting hundreds, thousands, billions of computers?
  - 하지만 수백, 수천, 수십억 대의 컴퓨터를 연결하는 것은 어떨까?
- Of course a single router can't scale that far, but, if you read carefully, we said that a router is a computer like any other, so what keeps us from connecting two routers together?
  - 물론 하나의 라우터가 그 정도까지 확장할 수 없다.
  - 하지만 신중히 읽어보면, 라우터는 다른 컴퓨터와 마찬가지로 컴퓨터라고 말했었다.
  - 그렇다면, 두 개의 라우터를 서로 연결하지 못하게 하는 것이 있을까?
- Nothing, so let's do that.
  - 없다.
  - 다음과 같이 해보자.

![img](/assets/img/mdn-internet-04.png)

<br>

- By connecting computers to routers, then routers to routers, we are able to scale infinitely.
  - 컴퓨터를 라우터에 연결한 다음, 라우터를 라우터에 연결하면 무한히 확장할 수 있다.

![img](/assets/img/mdn-internet-05.png)

<br>

- Such a network comes very close to what we call the Internet, but we're missing something.
  - 이러한 네트워크는 우리가 인터넷이라고 하는 것과 아주 유사하지만 무엇인가 빠졌다.
- We built that network for our own purposes.
  - 우리는 우리 자신의 목적을 위해 네트워크를 구축했다.
- There are other networks out there: your friends, your neighbors, anyone can have their own network of computers.
  - 또 다른 네트워크도 있다.
  - 당신의 친구, 당신의 이웃, 누구나 자기 자신의 컴퓨터 네트워크를 가질 수 있다.
- But it's not really possible to set cables up between your house and the rest of the world, so how can you handle this?
  - 하지만 당신의 집과 다른 지역 사이에 케이블을 연결할 수는 없다.
  - 이 문제를 어떻게 처리할 수 있을까?
- Well, there are already cables linked to your house, for example, electric power and telephone.
  - 이미 집에 연결된 케이블이 있다.
  - 전력과 전화이다.
- The telephone infrastructure already connects your house with anyone in the world so it is the perfect wire we need.
  - 전화 인프라는 이미 전 세계의 모든 사람과 집을 연결하므로, 우리가 필요로 하는 완벽한 전선이다.
- To connect our network to the telephone infrastructure, we need a special piece of equipment called a `modem`.
  - 우리의 네트워크를 전화 인프라에 연결하기 위해서는, `모뎀(modem)`이라는 특수 장비가 필요하다.
- This medem turns the information from our network into information manageable by the telephone infrastructure and vice versa.
  - 모뎀은 네트워크의 정보를 전화 인프라에서 처리할 수 있는 정보로 변경한다.
  - 그 반대의 경우도 마찬가지이다.

![img](/assets/img/mdn-internet-06.png)

<br>

- So we are connected to the telephone infrastructure.
  - 그래서 우리는 전화 인프라에 연결되어 있다.
- The next step is to send the messages from our network to the network we want to reach.
  - 다음 단계는, 우리의 네트워크에서 도달하고자 하는 네트워크로 메시지를 보내는 것이다.
- To do that, we will connect our network to an Internet Service Provider (ISP).
  - 이를 위해, 네트워크를 ISP (인터넷 서비스 제공사업자)에 연결한다.
- An ISP is a company that manages some special routers that are all linked together and can also access other ISPs' routers.
  - ISP는 서로 연결된 특수한 라우터를 관리하고, ISP의 라우터에도 액세스할 수 있는 회사이다.
- So the message from our network is carried through the network of ISP networks to the destination network.
  - 따라서 우리의 네트워크 메시지는 ISP 네트워크의 네트워크를 통해 대상 네트워크로 전달된다.
- The Internet consists of this whole infrastructure of networks.
  - 인터넷은 이러한 전체 네트워크 인프라로 구성된다.

![img](/assets/img/mdn-internet-07.png)

<br>

<br>

###### Finding computers (컴퓨터 찾기)

- If you want to send a message to a computer, you have to specify which one.
  - 컴퓨터로 메시지를 보내는 경우, 메시지를 받을 대상 컴퓨터를 지정해야 한다.
- Thus any computer linked to a network has a unique address that identifies it, called an "IP address" (where IP stands for *Internet Protocol*).
  - 따라서 네트워크에 연결된 모든 컴퓨터에는 "IP 주소" (IP는 *인터넷 규약*을 나타낸다)라고 하는 고유한 주소가 있다.
- It's an address made of a series of four numbers separated by dots, for example: `192.168.2.10`
  - `192.168.2.10`과 같이, 점으로 구분되어 있는 4개의 숫자로 구성된 주소이다.

<br>

- That's perfectly fine for computers, but we human begins have a hard time remembering that sort of address.
  - IP 주소는 컴퓨터에게 완벽하지만, 사람은 그런 종류의 주소를 기억하기 어렵다.
- To make things easier, we can alias an IP address with a human readable name called a *domain name*.
  - 그래서 사람이 읽을 수 있는, *도메인 이름*이라는 IP 주소의 이름을 지정할 수 있다.
- For example, `google.com` is the domain name used on top of the IP address `173.194.121.32`.
  - 예를 들어, ` google.com`은 IP 주소로 `173.194.121.31`이다.
- So using the domain name is the easiest way for us to reach a computer over the Internet.
  - 따라서 도메인 이름을 사용하는 것이 인터넷을 통해 컴퓨터에 접근하는 가장 쉬운 방법이다.

![img](/assets/img/mdn-internet-08.png)

<br>

<br>

###### Internet and the web (인터넷과 웹)

- As you might notice, when we browse the Web with a Web browser, we usually use the domain name to reach a website.
  - 알다시피, 웹 브라우저로 웹을 탐색할 때에는 일반적으로 도메인 이름을 사용해서 웹사이트에 접속한다.
- Does that mean the Internet and the Web are the same thing?
  - 그렇다면 인터넷과 웹이 같다고 할 수 있을까?
- It's not that simple.
  - 그렇게 간단하지가 않다.
- As we saw, the Internet is a technical infrastructure which allows billions of computers to be connected all together.
  - 앞에서 보았듯이, 인터넷은 수십억 대의 컴퓨터를 모두 연결하는 기술 인프라이다.
- Among those computers, some computers (called Web servers) can send messages intelligible to web browser.
  - 이러한 컴퓨터 중 일부 컴퓨터(웹 서버)는 웹 브라우저가 이해할 수 있는 메시지를 보낼 수 있다.
- The `Internet` is an infrastructure, whereas the `Web` is a service built on top of the infrastructure.
  - `인터넷`은 인프라이며, `웹`은 인프라를 기반으로 구축된 서비스이다.
- It is worth nothing there are several other services built on top of the Internet, such as email and IRC (Internet Red Cross).
  - 웹 뿐만 아니라, 인터넷을 기반으로 구축된 몇 가지 다른 서비스들(이메일 및 IRC와 같은)도 있다.

<br>

<br>