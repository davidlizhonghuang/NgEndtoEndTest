# Angular TDD development with Protractor 

<pre>
1, JavaScript development can be tested with different tools such as jasmine qunit
2, Jasmine is a good tool for Angular testing
3, Karma can do automate test in Jasmine
4, Protractor is invented for end to end testing of angular js

5, steps of protractor testing

        1, create a new dictionary c://protractor
        2, npm install -g protractor
        3, webdriver-manager update
        4, webdriver-manager start
          3 and 4 are used to run selenium server
        5, create a new spec.js in dictionary
        6, create a new conf.js in dictionary
        7, add code below to conf.js
        
            exports.config = {
              chromeOnly: true,
              framework: 'jasmine',
              seleniumAddress: 'http://localhost:4444/wd/hub',
              specs: ['spec.js'],
            };
        
        8, add below code to spec.js
        
            describe('Protractor Demo App', function () {
            it('should have a title', function () {
                browser.get('http://localhost:59636/E2Etest/Index');
                expect(browser.getTitle()).toEqual('e2e test page');
            });
            });
            
            or 
            describe('test ng-repeat',  function () {
            beforeEach(function () {  
                        browser.get('http://localhost:59636/E2Etest/Index');
                        var commentInput = $('input');
                        commentInput.sendKeys('key6'); 
                        var submitButton = element.all(by.buttonText('Submit')).click();
                     });
            it("get loop", function () {
                 var history = element.all(by.repeater('itm in plist'));
                  expect(history.count()).toBe(5); //success
                 var latestResult = element(by.binding('bbd')); 
                 expect(latestResult.getText()).toBe("binding bbd"); 
                 var item = $('.count .two');  //class name that is css
                 expect(item.getText()).toBe('Second'); //to get this class name
            });
            });
        
            or..............
        
          9, open a new cmd and run >potractor conf.js
          10, test will be run automatically and return success or failed logs
          11, use Protractor API 3.0 to develop spec.js file
          12, Karma will watch the change of codes and run the testing in real time
          13, browser.get(url) page should contain angular js code.
          14, we then can write different Jasmine test to test angualr js code and add those tested codes
          to js file used in html page.

therefore, we need a protractor test framework, a conf.js file  ,  a spec.js file , a cmd to run protractor server,
and a cmd to run protractor command for testing, and a html page we will develop and put tested angular js codes in.
it is easy to run after we get used to all of those procedures
</pre>

