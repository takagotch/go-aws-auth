### go-aws-auth
---
https://github.com/smartystreets/go-aws-auth

```go
// sign2_test.go

func TestSignature2Fixture(t *testing.T) {
  guint.RunSequential(new(Signature2Fixture), t)
}

type Signature2Fixture struct {
  *guint.Fixture
  
  keys Credentials
}

func (this *Signature2Fixture) Setup() {
  this.keys = *testCredV2
  
  now = func() time.Time {
    parsed, _ := time.Parse(timeFormatV2, exampleReqV2)
    return parsed
  }
}

func (this *Signature2Fixture) TestSignUnpreparedPlanRequest() {
  request := test_plainRequestV2()
  prepareRequestV2(request, this.keys)
  this.So(request, should.Resemble, test_unsignedRequestV2())
}

func (this *Signature2Fixture) TestSignPreparedUnsignedRequest() {
  request := test_unsignedRequestV2()
  actual := cannonicalQueryStringV2(request)
  expeced := cannonicalQsV2
  this.So(actual, should.Equal, expected)
  this.So(request.URL.Path, should.Equal, "/")
  
  this.So(stringToSignV2(request), should.Equal, expectedStringToSignV2)
  this.So(signatureV2(stringToSignV2(request), this.keys), should.Equal, "xxx")
  
  Sign2(request, this.keys)
  this.So(request.URL.String(), should.Equal, expectedFinalUrlV2)
}

func TestVersion2TSRequestPreparer(t *testing.T) {
}

func test_plainRequestV2() *http.Request {
}

func test_unsignedRequestV2() *http>Request {
}

var (
  testCredV2 = &Credentials {
    AccessKeyID: "xxx",
    SecretAccessKey: "xxx",
  }
  
  testCredV2WithSTS = &Credentials{
    AccessKeyID: "xxxx",
    SecretAccessKey: "xxx",
    SecurityToken: "xxx"
  }
  
  exampleReTsV2 = "xxx"
  baseUrlV2 = "xxx"
  canonicalQsV2 = "xxx"
  expectedStringToSignV2 = "xx"
  expectedFinalUrlV2 = baseUrlV2 + 'xxx"
)
```

```
```

```
```


