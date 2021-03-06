# JJBACSA-ANDROID

## ๐ฝ ์ฉ์ฉ๋ฐ์ฌ ์๋๋ก์ด๋ ์ฑ ๐ฝ

## Technology Stacks

- Kotlin
- Coroutine Flow
- Hilt
- Retrofit 2

## App Architecture

Clean architecture + MVVM Design pattern

### Layer Declaration

- domain
- data
- app

## Code Convention

> ์๋ ๋ช์๋ ์ปจ๋ฒค์์ ์์ธ๊ฐ ๋ฐ๊ฒฌ๋๋ฉด ์ด์๋ฅผ ์ด์ด์ ์ปจ๋ฒค์ ์ถ๊ฐ/์์  ๋ฑ ๊ฒํ 

### XML id

```
[view]_[where]_[purpose]
```

- [view] : View์ ์ด๋ฆ์ snack_case๋ก ๋ณํ
  - TextView -> text_view_...
  - RecyclerView -> recycler_view_...
  - Toolbar -> toolbar_...
- [where] : View๊ฐ ์์นํ ๊ณณ์ ๋ช์
  - Main screen text view -> text_view_main_...
- [purpose] : View์ ์ฌ์ฉ ์ฉ๋๋ฅผ ๋ช์
  - ๋ก๊ทธ์ธ->๋น๋ฐ๋ฒํธ ์๋ ฅ EditText -> edit_text_login_password

### Shape drawables (button shape, dialog shape, ...)

```
shape_[rect|circ|oval...](_[colorcode]_stroke)(_[colorcode]_solid)(_etc variables).xml
```

- shape_rect_ff1234_stroke_f1f2f3_solid_radius_4.xml
- shape_circ_4321fe_solid.xml

### State list drawables (checked, unchecked, selected, unselected, ...)

```
sel_[where]_[what].xml
```

### Kotlin code convention

- ktlint
- detekt

### Architectual convention

- usecase๊ฐ ๋จ์ repository๋ฅผ ํธ์ถํ๋ ๊ฒฝ์ฐ์๋ usecase ํ์ ์ ์ฉ
- usecase์ ๋ฐํ๊ฐ์ `kotlin.Result`๋ก ๋ํ
- API request/response <-> Repository Model ๊ฐ ๋งคํ(mapper ์ฌ์ฉ)

### Git convention

#### ๊ณตํต ์ฌํญ

[type]

- fix : ๋ฒ๊ทธ, ์ค๋ฅ ํด๊ฒฐ ```[fix] #10 - callback error```
- add : Feat ์ด์ธ์ ๋ถ์์ ์ธ ์ฝ๋ ์ถ๊ฐ, ๋ผ์ด๋ธ๋ฌ๋ฆฌ ์ถ๊ฐ, ์๋ก์ด View๋ Activity ์์ฑ ```[add] #11 - LoginActivity``` ```[add] #12 - CircleImageView Library```
- feat : ์๋ก์ด ๊ธฐ๋ฅ ๊ตฌํ ```[feat] #11 - google login```
- del : ์ธ๋ชจ์๋ ์ฝ๋ ์ญ์  [del] ```#12 - unnecessary import package```
- docs : README๋ WIKI ๋ฑ์ ๋ฌธ์ ๊ฐ์  ```[docs] update readme```
- refactor : ๋ด๋ถ ๋ก์ง์ ๋ณ๊ฒฝ ํ์ง ์๊ณ  ๊ธฐ์กด์ ์ฝ๋๋ฅผ ๊ฐ์ ํ๋ ๋ฆฌํฉํ ๋ง ์ [refactor] ```#15 - MVP architecture to MVVM```
- chore : ๊ทธ ์ด์ธ์ ์ก์ผ/ ๋ฒ์  ์ฝ๋ ์์ , ํจํค์ง ๊ตฌ์กฐ ๋ณ๊ฒฝ, ํ์ผ ์ด๋, ๊ฐ๋์ฑ์ด๋ ๋ณ์๋ช, reformat ๋ฑ [chore] #20 - delete unnecessary import package ```[chore] #21 - reformat MainActivity```
- ui : xml ํ์ผ๋ง ์์ ํ ๊ฒฝ์ฐ ```[ui] #30 - use constraintlayout in activity_main.xml```
- mod : ๊ทธ ์ธ์ ๋๋จธ์ง๋ฅผ ์์ ํ ๊ฒฝ์ฐ ```[mod] #31 - modify login process```
- test : ํ์คํธ ์ฝ๋ ์ถ๊ฐ

#### Issue

```
[[type]] ์์ ๋ด์ฉ
```

๋ชจ๋  ์์ ์  ์ด์ ์์ฑ์ด ์ ํ๋์ด์ผ ํ๋ค.

- [ui] Add login view
- [feat] Integrate login api

#### Branch

```
#[issue number]-[type] ์์-๋ด์ฉ
```

- #1-ui-Add-login-View
- #2-feat-Integrate-login-api

#### Commit Message

```
#[issue number] [[type]] [commit message]
```

commit message๋ ํ์ฌ ์์ ๋ก, ์ต๋ํ ๊ฐ๊ฒฐํ๊ฒ ์์ฑ

- #1 [ui] Make password invisible
- #1 [ui] Add sns login button

#### Pull Request

```
#[issue number] [[type]] ์์ ๋ด์ฉ
```

branch ์ด๋ฆ์ ๊ทธ๋๋ก ๋๊ฒจ๋ฐ์ ์์ฑ

