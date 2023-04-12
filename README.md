## Usage

In this app, a 3D model is loaded using the `GLTFLoader` from the `three-stdlib` package. The `useLoader` hook is used to asynchronously load the model and render it using the `primitive` component.

```javascript
const Model = () => {
  const gltf = useLoader(GLTFLoader, "/threedobject/scene.gltf");

  return (
    <>
      <primitive dispose={null} object={gltf.scene} scale={2} />
    </>
  );
};

This is a [Next.js](https://nextjs.org/) project bootstrapped with [`create-next-app`](https://github.com/vercel/next.js/tree/canary/packages/create-next-app).
```

The 3D scene is rendered using the Canvas component from @react-three/fiber. This component creates a WebGL canvas and renders the 3D scene using the three.js library.

```javascript

<Canvas shadows dpr={[1, 2]} camera={{ position: [8, 8, 4], fov: 100 }}>
  <ambientLight intensity={0.5} />
  <spotLight intensity={0.1} angle={0.6} penumbra={8} position={[10, 15, 10]} />

  <Suspense fallback={null}>
    <Model />
    <Environment preset="city" />
  </Suspense>
  <OrbitControls autoRotate />
</Canvas>



```

The OrbitControls component is used to enable camera controls in the scene, and the Environment component is used to create a background and lighting.

The size of the 3D container is styled using styled-components.

```javascript

const ThreeDContainer = styled.div`
  canvas {
    height: 660px !important;
    width: 400px !important;
  }
`;


```

## Contributing

Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

## Getting started

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

You can start editing the page by modifying `app/page.tsx`. The page auto-updates as you edit the file.

[http://localhost:3000/api/hello](http://localhost:3000/api/hello) is an endpoint that uses [Route Handlers](https://beta.nextjs.org/docs/routing/route-handlers). This endpoint can be edited in `app/api/hello/route.ts`.

This project uses [`next/font`](https://nextjs.org/docs/basic-features/font-optimization) to automatically optimize and load Inter, a custom Google Font.

## Learn More

To learn more about Next.js, take a look at the following resources:

- [Next.js Documentation](https://nextjs.org/docs) - learn about Next.js features and API.
- [Learn Next.js](https://nextjs.org/learn) - an interactive Next.js tutorial.

You can check out [the Next.js GitHub repository](https://github.com/vercel/next.js/) - your feedback and contributions are welcome!

## Deploy on Vercel

The easiest way to deploy your Next.js app is to use the [Vercel Platform](https://vercel.com/new?utm_medium=default-template&filter=next.js&utm_source=create-next-app&utm_campaign=create-next-app-readme) from the creators of Next.js.

Check out our [Next.js deployment documentation](https://nextjs.org/docs/deployment) for more details.
