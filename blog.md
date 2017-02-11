---
layout: page
title: Blog
permalink: /blog/
---
[Qunit]

@see http://blog.saltfactory.net/javascript-unit-test-using-with-qunit/

환경
Javascript + node.js(Server) + Qunit-2.1.1js + Qunit.css 사용

1. assert
- 로직의 이상유무를 판단할 수 있다.

2. assert.ok

3. assert.equal
- value 값을 비교
ex) assert.equal(1, 1, "Success!");

4. assert.deepEqual
-  value 값 뿐만 아니라 type까지 같이 확인하여 비교
ex) assert.deepEqual(1, "1", "1과 '1'은 서로 같음");

5. assert.strictEqual
- 4번과 마찬가지로 value, type 까지 비교
ex) assert.strictEqual(1, "1", "1 and 1 are the same value and type");

6. assert.expect
- 테스트를 포함하는게 몇개인지 확인 할 수 있게 도와주는 방식
ex)
    QUnit.test("hello test", function(assert){  
    	assert.expect(5);

        assert.ok( 1 == 1, "Passed!");
        assert.ok( 1 == "1", "Passed!");
        assert.equal(1, 1, "Passed!");
        assert.equal(1, "1", "Passed!");
        assert.ok( 1 == "1", "Passed!");
    });
- expect는 5개인데, 테스트하는 항목이 6개 즉 갯수가 일치하지 않으면 에러가 발생(갯수가 일치하지 않음)

7. QUnit.module
- 테스트 항목이 많아지면 확인 및 관리하기가 힘들기 때문에 모듈이리고하여 쉽게 구분할 수 있게 그룹핑한다고 생각하면 됨
ex)
    QUnit.module( "group a" );  
    QUnit.test( "a basic test example", function(assert) {  
    	assert.ok( true, "this test is fine" );
    });
    QUnit.test( "a basic test example 2", function(assert) {  
    	assert.ok( true, "this test is fine" );
    });

    QUnit.module( "group b" );  
    QUnit.test( "a basic test example 3", function(assert) {  
    	assert.ok( true, "this test is fine" );
    });
    QUnit.test( "a basic test example 4", function(assert) {  
    	assert.ok( true, "this test is fine" );
    });


[결과]

4년동안 웹을 개발하면서 자바스크립트에 대한 테스트는 브라우져 요소검사를 통해서만 확인하였다.=..=

Qunit을 공부하면서 결과값에 대한 Validation체크에 대해 가장 좋게 생각하는 부분이다.

예전에는 결과값이 잘 못되거나 에러가 발생하면 매번 디버깅을 통해 확인을 하다보니 지금생각해보면 많이 불편했던 것 같다.

JUnit처럼 자바스크립트도 구체적이고 안정성까지 보장된 테스트를 진행하는 것에 대해

앞으로 하는 프로젝트 또는 개발업무에 도입을 해봐야겠다.
