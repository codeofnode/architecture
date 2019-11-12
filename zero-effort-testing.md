# Testing should be effortless

## Integration test cases should be automatically generated from API Endpoints spec
Eg swagger spec already gives types of parameters it accepts, we can randomly generate one and fire the request

## Unit test cases should be automatically generated from module input and output spec
That is specified in comments above function.

## We should have a test case recorder (at least on alpha env and beta env) for both unit tests and integration test.
All we need is a proxy on API server side and on module side.
