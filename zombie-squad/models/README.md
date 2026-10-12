# 외부 3D 캐릭터 넣기

이 폴더에 `.glb` 파일과 `manifest.json`을 두면 게임이 자리표시자 대신 그 모델을 씁니다.
`manifest.json`이 없으면 기본 자리표시자(기사·고블린·오우거)가 그대로 나옵니다.

```json
{
  "hero":    "models/knight.glb",
  "soldier": "models/goblin.glb",
  "big":     "models/orc.glb",
  "boss":    "models/ogre.glb",
  "height":  { "hero": 1.75, "soldier": 1.15, "big": 1.6, "boss": 2.8 },
  "rotY":    { "hero": 0 },
  "anim":    { "soldier": { "walk": "Walking_A", "attack": "1H_Melee_Attack_Chop" } }
}
```

- `hero` 영웅, `soldier` 일반 적, `big` 큰 적, `boss` 보스. 있는 것만 적으면 됩니다.
- `height` 는 원하는 키(미터). 모델 크기는 자동으로 맞춰집니다. 생략하면 기본값.
- `rotY` 는 모델이 옆이나 뒤를 보고 있을 때 돌리는 각도(라디안, 3.1416 = 180도).
- `anim` 은 애니메이션 이름을 직접 지정할 때. 생략하면 이름에 walk/run, idle, attack 이 들어간 클립을 자동으로 찾습니다.
- Draco 압축된 glb 는 지원하지 않습니다(압축 없이 내보내기).
