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
        url: '/researchers/'
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
    id: location
    content:
      title: 📍 오시는 길
      subtitle: ''
      text: |-
        <div style="display:grid; grid-template-columns:1fr 1fr; gap:32px; align-items:start; margin-top:16px;">
          <div style="border-radius:8px; overflow:hidden; border:1px solid #ddd; min-height:340px;">
            <iframe
              src="https://www.google.com/maps?q=%EA%B2%BD%EA%B8%B0%EB%8F%84%20%EC%95%88%EC%82%B0%EC%8B%9C%20%EC%83%81%EB%A1%9D%EA%B5%AC%20%ED%95%AD%EA%B0%80%EC%9A%B8%EB%A1%9C%20143&output=embed"
              width="100%" height="340" style="border:0; display:block;" loading="lazy"
              referrerpolicy="no-referrer-when-downgrade">
            </iframe>
          </div>
          <div>
            <h3 style="margin-top:0;">Address</h3>
            <p>경기도 안산시 상록구 항가울로 143<br>KNICC-MSDTK (M&amp;S and DT Research Center of KITECH)</p>
            <h3>Contact</h3>
            <p>msdtk@kitech.re.kr</p>
          </div>
        </div>
    design:
      columns: '1'
---
