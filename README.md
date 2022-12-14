# quack-parse-version-actions

꽥꽥 배포용으로 사용되는 꽥꽥이 버전 조회 액션

## Inputs & Outputs

```yaml
inputs:
  path:
    description: '버전 파일 경로'
    required: true

outputs:
  version:
    description: '꽥꽥이 버전'
```

## Usage

```yaml
- uses: actions/checkout@v3 # require!

- name: Label filtering # require!
  id: label
  uses: duckie-team/quack-label-filter-actions@1.0.4
  with:
    labels: "${{ toJson(github.event.pull_request.labels.*.name) }}"

- name: Quack version parsing
  id: version
  uses: duckie-team/quack-parse-version-actions@1.0.1
  with:
    path: ${{ steps.label.outputs.version_path }}
```

---

자바스크립트를 8년전 프로그래밍 입문할 때 잠깐 배우고 아예 안써서... 생각나는 아주 기초적인 문법들만을 이용하여 제작하였습니다.
괜히 잘 모르는 영역까지 사용해서 코드 예쁘게 만들다가 시간 소비가 너무 많이 될 것 같아서... 그냥 이렇게 만들었습니다. 
