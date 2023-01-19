## Moon Tech RTK Query Practice

### Structure :

- src > features > api > apiSlice.js

### createApi initial set up : [help](https://redux-toolkit.js.org/tutorials/rtk-query#create-an-api-service)

- import { createApi } from "@reduxjs/toolkit/query/react"
- export const productApi = createApi({})
- - reducerPath
- - baseQuery
- - tagTypes
- - endpoints

### baseQuery

- baseQuery: fetchBaseQuery({}),
- - baseUrl: "http://localhost:5000"

### endpoints

- (builder) => ({}),
- - getProducts: builder.query({
- - - query: () => ({}),
- - - - url: "/product",

### store.js set up : [help](https://redux-toolkit.js.org/tutorials/rtk-query#add-the-service-to-your-store)

- configureStore({})
- - reducer: { [productApi.reducerPath]: productApi.reducer, }
- - middleware: (getDefaultMiddleware) => getDefaultMiddleware().concat(productApi.middleware),

#### refetchOnMountOrArgChange

- fetch data each time when the page render

#### Automated Re-fetching

- tagTypes
- - cache the tags
- providesTags
- - add tags in cache
- - re-fetch this query if those tags invalidated
- invalidatesTags
- - invalidates tags so that data can re-fetch.
