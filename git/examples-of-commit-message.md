# 커밋 메세지 작성 예시

커밋 메세지 기록 시에 자주 사용되는 단어 및 형식을 익히고자, 몇몇 유명한 오픈 소스 저장소들의 커밋 메세지 형식을 살펴보았다. 현재 나는 [Udacity 커밋 메세지 스타일 가이드](https://udacity.github.io/git-styleguide/)에 따라 커밋 메세지를 기록하고 있기 때문에, 이에 따라 가능한 같은 형식을 취하는 저장소를 기준으로 찾아보았다. 

## 타입에 따른 커밋 메세지 예시

### chore

* chore: Bump package dependencies (#137)
* chore: Remove class properties babel plugin and babel-eslint (#134)
* chore: Improve eslint glob and add lint-staged (#132)
* chore: Switch over to fixed versioning
* chore: Upgrade examples
* chore: Replace standard-changelog by standard-version
* chore: Remove renamed SpreadProperty checks

### feat

* feat: Abort and passthrough from an intercept (#57)
* feat: Class events and EventEmitter (#52)
* feat: Convert recordings to be HAR compliant (#45)
* feat: Make recording size limit configurable (#40)
* feat(core): Normalize headers by lower-casing all keys (#42)
* feat: Support `devtools` string on `Provider`
* feat: Support type cast expression when detecting components (#279)

### refactor

* refactor: Abstract `useContextState` and `useContextReducer` common stuff

### fix

* fix: Accept arguments other than objects in `createContext`
* fix: Make `initialAction` on `useContextReducer` synchronous on render
* fix: Ensure null is never put into visited types memory
* fix: resolve value to a proper node instead of an array (#278)
* fix: extract display name correctly even if components are wrapped (#277)

### docs

* docs: Document Jest & Jasmine support using setup-polly-jest (#135)
* docs: Fix small typo
* docs: Replace jsbin with codepen embed
* docs: Add jest with node-fetch example (#115)
* docs: Update readmes
* docs: Add cli option to README

### test

* test: Fix hanging jest test case (#130)
* test: Ignore coverage from useDevtools

## References

* [Netflix/pollyjs](https://github.com/Netflix/pollyjs)
* [diegohaz/constate](https://github.com/diegohaz/constate)
* [reactjs/react-docgen](https://github.com/reactjs/react-docgen)