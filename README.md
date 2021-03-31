[![CircleCI](https://circleci.com/gh/spring-cloud-incubator/spring-cloud-square.svg?style=svg)](https://circleci.com/gh/spring-cloud-incubator/spring-cloud-square)

# OkHttpClient integration with Spring Cloud

This module supplies integration with Square's [`OkHttpClient`](http://square.github.io/okhttp/) and  [Spring Cloud LoadBalancer](https://github.com/spring-cloud/spring-cloud-commons/spring-cloud-loadbalancer).

An application interceptor is added to the `OkHttpClient` created via autoconfiguration which resolves the scheme, host and port from Spring Cloud LoadBalancer and rewrites the url.

By supporting `OkHttpClient`, it enables Square's [Retrofit](http://square.github.io/retrofit/) to use  Spring Cloud LoadBalancer as well.

See [`OkHttpLoadBalancerInterceptorTests`](https://github.com/spring-cloud-incubator/spring-cloud-square/blob/master/spring-cloud-square-okhttp/src/test/java/org/springframework/cloud/square/okhttp/loadbalancer/OkHttpLoadBalancerInterceptorTests.java) for Spring Cloud LoadBalancer samples.

# Spring WebClient

Support was also added for Spring WebClient. This implements an `okhttp3.Call.Factory` that uses `WebClient` under the covers. This provides a fully non-blocking shim instead of using okhttp3.

See [`WebClientRetrofitTests`](https://github.com/spring-cloud-incubator/spring-cloud-square/blob/master/spring-cloud-square-retrofit-webclient/src/test/java/org/springframework/cloud/square/retrofit/webclient/WebClientRetrofitTests.java) for WebClient samples.
