### Node.js에서 NPM 명령어 사용하기

#### **1. npm install**
`npm install` 명령어는 Node Package Manager(NPM)를 사용하여 현재 프로젝트에서 필요한 모듈을 설치하는 데 사용됩니다. 이 명령어는 프로젝트 디렉토리에 존재하는 **`package.json`** 파일을 참고하여 필요한 의존성을 확인하고, 일괄적으로 설치합니다.

설치된 모듈은 프로젝트의 **`node_modules`** 디렉토리에 저장되며, 이후 프로젝트 실행 시 필요한 환경을 제공합니다. 

##### 예시:
```bash
npm install
```

#### **2. react-scripts 오류 해결**
```bash
npm install --save react-scripts
```
- 위 명령어는 프로젝트에서 **`react-scripts`** 모듈을 수동으로 설치할 때 사용됩니다.
- **`react-scripts`**는 React 애플리케이션에서 자주 사용하는 스크립트를 포함하고 있으며, 프로젝트 빌드 및 실행 과정에서 중요한 역할을 합니다.
  
**오류 발생 시 대처 방법:**
- **`'react-scripts' is not an internal or external command`** 오류는 `react-scripts` 모듈이 설치되지 않았거나 손상된 경우 발생할 수 있습니다.
- 이 경우:
  1. **`npm install --save react-scripts`** 명령어를 실행하여 `react-scripts`를 설치합니다.
  2. **`package.json`** 파일의 `dependencies` 섹션에서 `react-scripts`의 버전을 확인하세요. 버전에 맞는 `react-scripts`가 설치되었는지 점검하고, 필요 시 버전을 명시하여 재설치합니다:
     ```bash
     npm install react-scripts@<버전>
     ```
  3. 모든 설치 후에도 오류가 지속된다면, 프로젝트의 **`node_modules`** 디렉토리와 **`package-lock.json`** 파일을 삭제하고 의존성을 다시 설치합니다:
     ```bash
     rm -rf node_modules package-lock.json
     npm install
     ```

#### **3. npm start**
`npm start` 명령어는 React 애플리케이션을 개발 모드로 실행합니다. 실행 후 기본적으로 **`http://localhost:3000`** 주소에서 브라우저를 통해 애플리케이션을 확인할 수 있습니다.

- 애플리케이션이 실행되면, **Hot Module Replacement(HMR)** 기능을 통해 코드 변경 사항이 즉시 반영됩니다. 페이지를 새로고침하지 않아도 최신 변경 사항을 확인할 수 있습니다.
- 실행 중 콘솔에서 발생하는 오류를 실시간으로 확인하고, 문제를 빠르게 해결할 수 있습니다.

##### 예시:
```bash
npm start
```

##### 동작 과정:
1. 프로젝트 디렉토리에서 `npm start` 명령어 실행.
2. React 개발 서버가 시작되며 **`http://localhost:3000`** 주소에서 애플리케이션 확인.
3. 코드 변경 시 자동으로 브라우저가 새로고침되어 변경 사항을 반영.

#### **주의사항**
- `npm install` 또는 `npm start` 명령 실행 시 예상치 못한 오류가 발생할 경우, Node.js 버전이 프로젝트와 호환되지 않을 수 있습니다. `node -v` 명령어를 통해 현재 Node.js 버전을 확인하고, 프로젝트 요구사항에 맞는 버전으로 업데이트하세요.
- React 프로젝트의 의존성 파일, 특히 `package.json`을 수정하거나 버전을 변경할 때는 주의가 필요합니다. 의존성 충돌이 발생할 수 있으므로 항상 최신 버전을 확인하고 관리하세요.
