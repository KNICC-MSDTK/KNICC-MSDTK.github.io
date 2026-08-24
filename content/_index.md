---
title: ''
summary: ''
date: 2026-08-23
type: landing

sections:
  - block: hero
    content:
      title: KNICC-MSDTK
      text: |-
        M&S and DT Research Center of KITECH

        가상과 현실을 잇는 모델링·시뮬레이션(M&S)으로, 산업 현장의 디지털트윈을 만듭니다.
        한국생산기술연구원(KITECH) 소속 연구센터로서, 제조 공정과 설비를 가상 공간에 재현하여
        예측·최적화·검증이 가능한 기술을 연구합니다.
      primary_action:
        text: 연구분야 보기
        url: '#research'
      secondary_action:
        text: 구성원 보기
        url: '#people'
    design:
      background:
        gradient_mesh:
          enable: true
      name:
        size: md
      avatar:
        size: medium
        shape: circle

  - block: markdown
    id: about
    content:
      title: 📌 센터 소개
      subtitle: ''
      text: |-
        KNICC-MSDTK(M&S and DT Research Center of KITECH)는 모델링·시뮬레이션(M&S) 기술을 기반으로
        물리 세계와 가상 세계를 정교하게 연결하는 디지털트윈을 연구합니다. 제조 공정, 설비, 생산
        시스템을 가상 공간에 재현하여 예측·최적화·검증이 가능한 기술을 개발합니다.

        나아가 사이버물리시스템(CPS), 실시간 데이터 연동, 스마트 제조로 연구 영역을 확장하여
        조선·기계·에너지 등 다양한 산업 분야에 실질적으로 적용 가능한 디지털트윈 기술을 연구합니다.
    design:
      columns: '1'

  - block: features
    id: research
    content:
      title: 🔬 핵심 연구 분야
      subtitle: ''
      items:
        - name: 모델링 & 시뮬레이션
          icon: cog
          description: 공정·설비의 물리 기반 모델링과 시뮬레이션으로 설계·운영을 사전에 검증하고 최적화합니다.
        - name: 디지털트윈
          icon: cube
          description: 제조 설비와 생산 시스템을 가상 공간에 재현해 실시간으로 상태를 동기화하는 플랫폼을 개발합니다.
        - name: 사이버물리시스템(CPS)
          icon: cpu-chip
          description: 센서·제어 데이터를 실시간으로 연동해 물리 시스템과 가상 모델이 함께 동작하는 환경을 구축합니다.
    design:
      columns: 3

  - block: markdown
    id: people
    content:
      title: 👥 구성원
      subtitle: ''
      text: |-
        디지털트윈·M&S·CPS 연구를 이끄는 연구진을 소개합니다.

        <a href="/researchers/" style="display:inline-block; margin-top:12px; padding:10px 22px; background:#c98a3e; color:#171106; border-radius:4px; font-weight:600; text-decoration:none;">구성원 보기 →</a>
    design:
      columns: '1'

  - block: collection
    id: projects
    content:
      title: 🗂️ 프로젝트
      text: ''
      filters:
        folders:
          - projects
    design:
      view: article-grid
      columns: 3

  - block: cta-card
    id: contact
    content:
      title: 📬 문의
      text: |-
        협력 및 채용 문의는 아래 이메일로 연락해 주세요.

        msdtk@kitech.re.kr
      button:
        text: 이메일 보내기
        url: mailto:msdtk@kitech.re.kr
    design:
      card:
        css_class: 'bg-gradient-to-br from-primary-500 via-primary-600 to-secondary-600 text-white shadow-2xl'
        css_style: ''
---
