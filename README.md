## Moon Tech RTK Query Practice

### Structure :

- src > features > api > apiSlice.js

### createApi initial set up : [help](https://redux-toolkit.js.org/tutorials/rtk-query#create-an-api-service)

- import { createApi } from "@reduxjs/toolkit/query/react"
- export const productApi = createApi({})
- - reducerPath
- - baseQuery

### baseQuery

- baseQuery: fetchBaseQuery({}),
- -

### store.js set up : [help](https://redux-toolkit.js.org/tutorials/rtk-query#add-the-service-to-your-store)

- configureStore({})
- - reducer: { [productApi.reducerPath]: productApi.reducer, }
- - middleware: (getDefaultMiddleware) => getDefaultMiddleware().concat(productApi),
