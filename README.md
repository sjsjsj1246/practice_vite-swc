# vite 사용기

다음과 같은 명령어로 바로 프로젝트를 생성할 수 있습니다.

```bash
npm create vite 프로젝트명 --template react-ts
```

package.json

```json
{
  "name": "practice_vite",
  "private": true,
  "version": "0.0.0",
  "type": "module",
  "scripts": {
    "dev": "vite",
    "build": "tsc && vite build",
    "preview": "vite preview"
  },
  "dependencies": {
    "react": "^18.2.0",
    "react-dom": "^18.2.0"
  },
  "devDependencies": {
    "@types/react": "^18.0.28",
    "@types/react-dom": "^18.0.11",
    "@vitejs/plugin-react": "^3.1.0",
    "typescript": "^4.9.3",
    "vite": "^4.2.0"
  }
}
```

- vite와 @vitejs/plugin-react 라는 의존성이 눈에 띕니다.

vite.config.ts

```tsx
import { defineConfig } from "vite";
import react from "@vitejs/plugin-react";

// https://vitejs.dev/config/
export default defineConfig({
  plugins: [react()],
});
```

config 파일이 ts로 되어있어 Definition을 찾아보며 작성할 수 있어 좋은 것 같습니다.

저는 babel이 아닌 SWC를 사용하고 싶어 @vitejs/plugin-react-swc 플러그인을 설치하고 적용했습니다.

```bash
pnpm i -D @vitejs/plugin-react-swc
```

```tsx
import { defineConfig } from "vite";
import react from "@vitejs/plugin-react-swc";

// https://vitejs.dev/config/
export default defineConfig({
  plugins: [react()],
});
```

build시간이 말도안되게 빠릅니다.

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/97c272a9-5aac-48cf-ae4e-11a4d36ad238/Untitled.png)

이제 create-react-app은 놔줘야 할 떄가 된 것 같습니다
