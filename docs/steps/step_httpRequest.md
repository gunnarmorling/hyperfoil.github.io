# httpRequest

Issues a HTTP request and registers handlers for the response.

| Property | Type | Description |
| ------- | ------- | -------- |
| authority | String | HTTP authority (host:port) this request should target. Must match one of the entries in <code>http</code> section. The string can use <a href="https://hyperfoil.io/userguide/benchmark/variables.html#string-interpolation">string interpolation</a>. |
| authority (alternative)| [Builder](#authority) | HTTP authority (host:port) this request should target. Must match one of the entries in <code>http</code> section. |
| body | [Builder](#body) | HTTP request body. |
| body (alternative)| String | HTTP request body (possibly a <a href="https://hyperfoil.io/userguide/benchmark/variables.html#string-interpolation">pattern</a>). |
| compensation | [Builder](#compensation) | Configures additional metric compensated for coordinated omission. |
| compression | [Builder](#compression) | Configure response compression. |
| compression (alternative)| String | Request server to respond with compressed entity using specified content encoding. |
| CONNECT | String | Issue HTTP CONNECT request to given path. This can be a <a href="https://hyperfoil.io/userguide/benchmark/variables.html#string-interpolation">pattern</a>. |
| CONNECT (alternative)| [Builder](#connect) | Issue HTTP CONNECT request to given path. |
| DELETE | String | Issue HTTP DELETE request to given path. This can be a <a href="https://hyperfoil.io/userguide/benchmark/variables.html#string-interpolation">pattern</a>. |
| DELETE (alternative)| [Builder](#delete) | Issue HTTP DELETE request to given path. |
| endpoint | [Builder](#endpoint) | HTTP endpoint this request should target. Must match to the <code>name</code> of the entries in <code>http</code> section. |
| GET | String | Issue HTTP GET request to given path. This can be a <a href="https://hyperfoil.io/userguide/benchmark/variables.html#string-interpolation">pattern</a>. |
| GET (alternative)| [Builder](#get) | Issue HTTP GET request to given path. |
| handler | [Builder](#handler) | HTTP response handlers. |
| HEAD | String | Issue HTTP HEAD request to given path. This can be a <a href="https://hyperfoil.io/userguide/benchmark/variables.html#string-interpolation">pattern</a>. |
| HEAD (alternative)| [Builder](#head) | Issue HTTP HEAD request to given path. |
| headers | [Builder](#headers) | HTTP headers sent in the request. |
| method | enum | HTTP method used for the request.<br>Options:{::nomarkdown}<ul><li><code>GET</code></li><li><code>HEAD</code></li><li><code>POST</code></li><li><code>PUT</code></li><li><code>DELETE</code></li><li><code>OPTIONS</code></li><li><code>PATCH</code></li><li><code>TRACE</code></li><li><code>CONNECT</code></li></ul>{:/} |
| metric | String | Requests statistics will use this metric name. |
| metric (alternative)| [&lt;list of strings&gt;](#metric) | Allows categorizing request statistics into metrics based on the request path. |
| OPTIONS | String | Issue HTTP OPTIONS request to given path. This can be a <a href="https://hyperfoil.io/userguide/benchmark/variables.html#string-interpolation">pattern</a>. |
| OPTIONS (alternative)| [Builder](#options) | Issue HTTP OPTIONS request to given path. |
| PATCH | String | Issue HTTP PATCH request to given path. This can be a <a href="https://hyperfoil.io/userguide/benchmark/variables.html#string-interpolation">pattern</a>. |
| PATCH (alternative)| [Builder](#patch) | Issue HTTP PATCH request to given path. |
| path | String | HTTP path (absolute or relative), including query and fragment. The string can use <a href="https://hyperfoil.io/userguide/benchmark/variables.html#string-interpolation">string interpolation</a>. |
| path (alternative)| [Builder](#path) | HTTP path (absolute or relative), including query and fragment. |
| POST | String | Issue HTTP POST request to given path. This can be a <a href="https://hyperfoil.io/userguide/benchmark/variables.html#string-interpolation">pattern</a>. |
| POST (alternative)| [Builder](#post) | Issue HTTP POST request to given path. |
| PUT | String | Issue HTTP PUT request to given path. This can be a <a href="https://hyperfoil.io/userguide/benchmark/variables.html#string-interpolation">pattern</a>. |
| PUT (alternative)| [Builder](#put) | Issue HTTP PUT request to given path. |
| sla | [Builder](#sla) | List of SLAs the requests are subject to. |
| sync | boolean | This request is synchronous; execution of the sequence does not continue until the full response is received. If this step is executed from multiple parallel instances of this sequence the progress of all sequences is blocked until there is a request in flight without response. <p> Default is <code>true</code>. |
| timeout | String | Request timeout - after this time the request will be marked as failed and connection will be closed. <p> Defaults to value set globally in <code>http</code> section. |
| TRACE | String | Issue HTTP TRACE request to given path. This can be a <a href="https://hyperfoil.io/userguide/benchmark/variables.html#string-interpolation">pattern</a>. |
| TRACE (alternative)| [Builder](#trace) | Issue HTTP TRACE request to given path. |

### <a id="authority"></a>authority

Generic builder for generating a string.


| Inline definition |
| -------- |
| A pattern for <a href="https://hyperfoil.io/userguide/benchmark/variables.html#string-interpolation">string interpolation</a>. |

| Property | Type | Description |
| ------- | ------- | ------- |
| fromVar | Object | Load the string from session variable. |
| pattern | String | Use <a href="https://hyperfoil.io/userguide/benchmark/variables.html#string-interpolation">pattern</a> replacing session variables. |
| value | String | String value used verbatim. |

### <a id="body"></a>body

Allows building HTTP request body from session variables.

| Property | Type | Description |
| ------- | ------- | ------- |
| form | [Builder](#bodyform) | Build form as if we were sending the request using HTML form. This option automatically adds <code>Content-Type: application/x-www-form-urlencoded</code> to the request headers. |
| fromFile | String | Send contents of the file. Note that this method does NOT set content-type automatically. |
| fromVar | String | Use variable content as request body. |
| pattern | String | <a href="https://hyperfoil.io/userguide/benchmark/variables.html#string-interpolation">Pattern</a> replacing <code>${sessionvar}</code> with variable contents in a string. |
| text | String | String sent as-is. |

### <a id="body.form"></a>body.form

| Property | Type | Description |
| ------- | ------- | ------- |
| &lt;list of mappings&gt; | [&lt;list of builders&gt;](#bodyformlist-of-mappings) | Add input pair described in the mapping. |

### <a id="body.form.&lt;list of mappings&gt;"></a>body.form.&lt;list of mappings&gt;

Form element (e.g. as if coming from an INPUT field).

| Property | Type | Description |
| ------- | ------- | ------- |
| fromVar | String | Input field value from session variable. |
| name | String | Input field name. |
| pattern | String | Input field value replacing session variables in a <a href="https://hyperfoil.io/userguide/benchmark/variables.html#string-interpolation">pattern</a>, e.g. <code>foo${myvariable}var</code> |
| value | String | Input field value (verbatim). |

### <a id="compensation"></a>compensation

| Property | Type | Description |
| ------- | ------- | ------- |
| metric | String | Metric name for the compensated results. |
| metric (alternative)| [&lt;list of strings&gt;](#compensationmetric) | Configure a custom metric for the compensated results. |
| targetRate | double | Desired rate of new virtual users per second. This is similar to <code>constantRate.usersPerSec</code> phase settings but works closer to legacy benchmark drivers by fixing the concurrency. |
| targetRate (alternative)| [Builder](#compensationtargetrate) | Desired rate of new virtual users per second. This is similar to <code>constantRate.usersPerSec</code> phase settings but works closer to legacy benchmark drivers by fixing the concurrency. |

### <a id="compensation.metric"></a>compensation.metric

Configure a custom metric for the compensated results.

| Property | Type | Description |
| ------- | ------- | ------- |
| &lt;list of strings&gt; | &lt;list of strings&gt; | {::nomarkdown}Allows categorizing request statistics into metrics based on the request path. The expressions are evaluated in the order as provided in the list. Use one of: <ul> <li><code>regexp -&gt; replacement</code>, e.g. <code>([^?]*)(\?.*)? -&gt; $1</code> to drop the query part. <li><code>regexp</code> (don't do any replaces and use the full path), e.g. <code>.*.jpg</code> <li><code>-&gt; name</code> (metric applied if none of the previous expressions match). </ul>{:/} |

### <a id="compensation.targetRate"></a>compensation.targetRate

| Property | Type | Description |
| ------- | ------- | ------- |
| base | double | Base value used for first iteration. |
| increment | double | Value by which the base value is incremented for each (but the very first) iteration. |

### <a id="compression"></a>compression

| Property | Type | Description |
| ------- | ------- | ------- |
| encoding | String | Encoding used for <code>Accept-Encoding</code>/<code>TE</code> header. The only currently supported is <code>gzip</code>. |
| type | enum | Type of compression (resource vs. transfer based).<br>Options:{::nomarkdown}<ul><li><code>CONTENT_ENCODING</code>: {:/}Use <code>Accept-Encoding</code> in request and expect <code>Content-Encoding</code> in response.{::nomarkdown}</li><li><code>TRANSFER_ENCODING</code>: {:/}Use <code>TE</code> in request and expect <code>Transfer-Encoding</code> in response.{::nomarkdown}</li></ul>{:/} |

### <a id="CONNECT"></a>CONNECT

Generic builder for generating a string.


| Inline definition |
| -------- |
| A pattern for <a href="https://hyperfoil.io/userguide/benchmark/variables.html#string-interpolation">string interpolation</a>. |

| Property | Type | Description |
| ------- | ------- | ------- |
| fromVar | Object | Load the string from session variable. |
| pattern | String | Use <a href="https://hyperfoil.io/userguide/benchmark/variables.html#string-interpolation">pattern</a> replacing session variables. |
| value | String | String value used verbatim. |

### <a id="DELETE"></a>DELETE

Generic builder for generating a string.


| Inline definition |
| -------- |
| A pattern for <a href="https://hyperfoil.io/userguide/benchmark/variables.html#string-interpolation">string interpolation</a>. |

| Property | Type | Description |
| ------- | ------- | ------- |
| fromVar | Object | Load the string from session variable. |
| pattern | String | Use <a href="https://hyperfoil.io/userguide/benchmark/variables.html#string-interpolation">pattern</a> replacing session variables. |
| value | String | String value used verbatim. |

### <a id="endpoint"></a>endpoint

Generic builder for generating a string.


| Inline definition |
| -------- |
| A pattern for <a href="https://hyperfoil.io/userguide/benchmark/variables.html#string-interpolation">string interpolation</a>. |

| Property | Type | Description |
| ------- | ------- | ------- |
| fromVar | Object | Load the string from session variable. |
| pattern | String | Use <a href="https://hyperfoil.io/userguide/benchmark/variables.html#string-interpolation">pattern</a> replacing session variables. |
| value | String | String value used verbatim. |

### <a id="GET"></a>GET

Generic builder for generating a string.


| Inline definition |
| -------- |
| A pattern for <a href="https://hyperfoil.io/userguide/benchmark/variables.html#string-interpolation">string interpolation</a>. |

| Property | Type | Description |
| ------- | ------- | ------- |
| fromVar | Object | Load the string from session variable. |
| pattern | String | Use <a href="https://hyperfoil.io/userguide/benchmark/variables.html#string-interpolation">pattern</a> replacing session variables. |
| value | String | String value used verbatim. |

### <a id="handler"></a>handler

Manages processing of HTTP responses.

| Property | Type | Description |
| ------- | ------- | ------- |
| autoRangeCheck | boolean | Inject status handler that marks the request as invalid on status 4xx or 5xx. Default value depends on <code>ergonomics.autoRangeCheck</code> (see <a href="https://hyperfoil.io/userguide/benchmark/ergonomics.html">User Guide</a>). |
| body | [Processor.Builder](index.html#processors) | Handle HTTP response body. |
| followRedirect | enum | Automatically fire requests when the server responds with redirection. Default value depends on <code>ergonomics.followRedirect</code> (see <a href="https://hyperfoil.io/userguide/benchmark/ergonomics.html">User Guide</a>).<br>Options:{::nomarkdown}<ul><li><code>NEVER</code>: {:/}Do not insert any automatic redirection handling.{::nomarkdown}</li><li><code>LOCATION_ONLY</code>: {:/}Redirect only upon status 3xx accompanied with a 'location' header. Status, headers, body and completions handlers are suppressed in this case (only raw-bytes handlers are still running). This is the default option.{::nomarkdown}</li><li><code>HTML_ONLY</code>: {:/}Handle only HTML response with META refresh header. Status, headers and body handlers are invoked both on the original response and on the response from subsequent requests. Completion handlers are suppressed on this request and invoked after the last response arrives (in case of multiple redirections).{::nomarkdown}</li><li><code>ALWAYS</code>: {:/}Implement both status 3xx + location and HTML redirects.{::nomarkdown}</li></ul>{:/} |
| header | [HeaderHandler.Builder](#handlerheader) | Handle HTTP response headers. |
| onCompletion | [Action.Builder](index.html#actions) | Action executed when the HTTP response is fully received. |
| rawBytes | [RawBytesHandler.Builder](#handlerrawbytes) | Handler processing HTTP response before parsing. |
| status | [StatusHandler.Builder](#handlerstatus) | Handle HTTP response status. |
| stopOnInvalid | boolean | Inject completion handler that will stop the session if the request has been marked as invalid. Default value depends on <code>ergonomics.stopOnInvalid</code> (see <a href="https://hyperfoil.io/userguide/benchmark/ergonomics.html">User Guide</a>). |

### <a id="handler.header"></a>handler.header

Handle HTTP response headers.

| Property | Type | Description |
| ------- | ------- | ------- |
| conditional | [ConditionalHeaderHandler.Builder](#handlerheaderconditional) | Passes the headers to nested handler if the condition holds. Note that the condition may be evaluated multiple times and therefore any nested handlers should not change the results of the condition. |
| countHeaders | CountHeadersHandler.Builder | Stores number of occurences of each header in custom statistics (these can be displayed in CLI using the <code>stats -c</code> command). |
| filter | [FilterHeaderHandler.Builder](#handlerheaderfilter) | Compares if the header name matches expression and invokes a processor with the value. |
| logInvalid | LogInvalidHandler.HeaderHandlerBuilder | Logs headers from requests marked as invalid. |
| recordHeaderTime | [RecordHeaderTimeHandler.Builder](#handlerheaderrecordheadertime) | Records alternative metric based on values from a header (e.g. when a proxy reports processing time). |

### <a id="handler.header.conditional"></a>handler.header.conditional

Passes the headers to nested handler if the condition holds. Note that the condition may be evaluated multiple times and therefore any nested handlers should not change the results of the condition.

| Property | Type | Description |
| ------- | ------- | ------- |
| allConditions | [Builder](#handlerheaderconditionalallconditions) | Condition combining multiple other conditions with 'AND' logic. |
| boolCondition | [Builder](#handlerheaderconditionalboolcondition) | Condition comparing boolean variables. |
| handler | [HeaderHandler.Builder](#handlerheaderconditionalhandler) | One or more header handlers that should be invoked. |
| intCondition | [Builder](#handlerheaderconditionalintcondition) | Condition comparing integer variables. |
| stringCondition | [Builder](#handlerheaderconditionalstringcondition) | Condition comparing string variables. |

### <a id="handler.header.conditional.allConditions"></a>handler.header.conditional.allConditions

Test more conditions and combine the results using AND logic.

| Property | Type | Description |
| ------- | ------- | ------- |
| &lt;list of mappings&gt; | [&lt;list of builders&gt;](#handlerheaderconditionalallconditionslist-of-mappings) | List of conditions. |

### <a id="handler.header.conditional.allConditions.&lt;list of mappings&gt;"></a>handler.header.conditional.allConditions.&lt;list of mappings&gt;

Selector for condition type.

| Property | Type | Description |
| ------- | ------- | ------- |
| allConditions | [Builder](#handlerheaderconditionalallconditionslist-of-mappingsallconditions) | Condition combining multiple other conditions with 'AND' logic. |
| boolCondition | [Builder](#handlerheaderconditionalallconditionslist-of-mappingsboolcondition) | Condition comparing boolean variables. |
| intCondition | [Builder](#handlerheaderconditionalallconditionslist-of-mappingsintcondition) | Condition comparing integer variables. |
| stringCondition | [Builder](#handlerheaderconditionalallconditionslist-of-mappingsstringcondition) | Condition comparing string variables. |

### <a id="handler.header.conditional.allConditions.&lt;list of mappings&gt;.allConditions"></a>handler.header.conditional.allConditions.&lt;list of mappings&gt;.allConditions

Test more conditions and combine the results using AND logic.

| Property | Type | Description |
| ------- | ------- | ------- |
| &lt;list of mappings&gt; | [&lt;list of builders&gt;](#handlerheaderconditionalallconditionslist-of-mappings) | List of conditions. |

### <a id="handler.header.conditional.allConditions.&lt;list of mappings&gt;.boolCondition"></a>handler.header.conditional.allConditions.&lt;list of mappings&gt;.boolCondition

Tests session variable containing boolean value.

| Property | Type | Description |
| ------- | ------- | ------- |
| fromVar | String | Variable name. |
| value | boolean | Expected value. |

### <a id="handler.header.conditional.allConditions.&lt;list of mappings&gt;.intCondition"></a>handler.header.conditional.allConditions.&lt;list of mappings&gt;.intCondition

Condition comparing integer in session variable.


| Inline definition |
| -------- |
| Parses condition in the form &lt;variable&gt; &lt;operator&gt; &lt;value&gt;
             where operator is one of: <code>==</code>, <code>!=</code>,
             <code>&lt;&gt;</code> (the same as <code>!=</code>),
             <code>&gt;=</code>, <code>&gt;</code>, <code>&lt;=</code>, <code>&lt;</code>. |

| Property | Type | Description |
| ------- | ------- | ------- |
| equalTo | [Builder](#handlerheaderconditionalintconditionequalto) | Compared variable must be equal to this value. |
| fromVar | Object | Variable name. |
| greaterOrEqualTo | [Builder](#handlerheaderconditionalintconditiongreaterorequalto) | Compared variable must be greater or equal to this value. |
| greaterThan | [Builder](#handlerheaderconditionalintconditiongreaterthan) | Compared variable must be greater than this value. |
| isSet | boolean | Check if the value is set or unset. By default the variable must be set. |
| lessOrEqualTo | [Builder](#handlerheaderconditionalintconditionlessorequalto) | Compared variable must be lower or equal to this value. |
| lessThan | [Builder](#handlerheaderconditionalintconditionlessthan) | Compared variable must be lower than this value. |
| notEqualTo | [Builder](#handlerheaderconditionalintconditionnotequalto) | Compared variable must not be equal to this value. |

### <a id="handler.header.conditional.allConditions.&lt;list of mappings&gt;.stringCondition"></a>handler.header.conditional.allConditions.&lt;list of mappings&gt;.stringCondition

Condition comparing string in session variable.

| Property | Type | Description |
| ------- | ------- | ------- |
| caseSensitive | boolean | True if the case must match, false if the check is case-insensitive. |
| endsWith | CharSequence | Suffix for the string. |
| equalTo | CharSequence | Literal value the string should match (the same as {@link #value}). |
| fromVar | Object | Variable name. |
| isSet | boolean | Check if the value is set or unset. By default the variable must be set. |
| length | int | Check the length of the string. |
| length (alternative)| [Builder](#handlerheaderconditionalstringconditionlength) | Check the length of the string. |
| matchVar | String | Fetch the value from a variable. |
| negate | boolean | Invert the logic of this condition. Defaults to false. |
| notEqualTo | CharSequence | Value that the string must not match. |
| startsWith | CharSequence | Prefix for the string. |
| value | CharSequence | Literal value the string should match. |

### <a id="handler.header.conditional.boolCondition"></a>handler.header.conditional.boolCondition

Tests session variable containing boolean value.

| Property | Type | Description |
| ------- | ------- | ------- |
| fromVar | String | Variable name. |
| value | boolean | Expected value. |

### <a id="handler.header.conditional.handler"></a>handler.header.conditional.handler

One or more header handlers that should be invoked.

| Property | Type | Description |
| ------- | ------- | ------- |
| conditional | [ConditionalHeaderHandler.Builder](#handlerheaderconditional) | Passes the headers to nested handler if the condition holds. Note that the condition may be evaluated multiple times and therefore any nested handlers should not change the results of the condition. |
| countHeaders | CountHeadersHandler.Builder | Stores number of occurences of each header in custom statistics (these can be displayed in CLI using the <code>stats -c</code> command). |
| filter | [FilterHeaderHandler.Builder](#handlerheaderfilter) | Compares if the header name matches expression and invokes a processor with the value. |
| logInvalid | LogInvalidHandler.HeaderHandlerBuilder | Logs headers from requests marked as invalid. |
| recordHeaderTime | [RecordHeaderTimeHandler.Builder](#handlerheaderrecordheadertime) | Records alternative metric based on values from a header (e.g. when a proxy reports processing time). |

### <a id="handler.header.conditional.intCondition"></a>handler.header.conditional.intCondition

Condition comparing integer in session variable.


| Inline definition |
| -------- |
| Parses condition in the form &lt;variable&gt; &lt;operator&gt; &lt;value&gt;
             where operator is one of: <code>==</code>, <code>!=</code>,
             <code>&lt;&gt;</code> (the same as <code>!=</code>),
             <code>&gt;=</code>, <code>&gt;</code>, <code>&lt;=</code>, <code>&lt;</code>. |

| Property | Type | Description |
| ------- | ------- | ------- |
| equalTo | [Builder](#handlerheaderconditionalintconditionequalto) | Compared variable must be equal to this value. |
| fromVar | Object | Variable name. |
| greaterOrEqualTo | [Builder](#handlerheaderconditionalintconditiongreaterorequalto) | Compared variable must be greater or equal to this value. |
| greaterThan | [Builder](#handlerheaderconditionalintconditiongreaterthan) | Compared variable must be greater than this value. |
| isSet | boolean | Check if the value is set or unset. By default the variable must be set. |
| lessOrEqualTo | [Builder](#handlerheaderconditionalintconditionlessorequalto) | Compared variable must be lower or equal to this value. |
| lessThan | [Builder](#handlerheaderconditionalintconditionlessthan) | Compared variable must be lower than this value. |
| notEqualTo | [Builder](#handlerheaderconditionalintconditionnotequalto) | Compared variable must not be equal to this value. |

### <a id="handler.header.conditional.intCondition.equalTo"></a>handler.header.conditional.intCondition.equalTo


| Inline definition |
| -------- |
| Uses the argument as a constant value. |

| Property | Type | Description |
| ------- | ------- | ------- |
| fromVar | String | Input variable name. |
| value | int | Value (integer). |

### <a id="handler.header.conditional.intCondition.greaterOrEqualTo"></a>handler.header.conditional.intCondition.greaterOrEqualTo


| Inline definition |
| -------- |
| Uses the argument as a constant value. |

| Property | Type | Description |
| ------- | ------- | ------- |
| fromVar | String | Input variable name. |
| value | int | Value (integer). |

### <a id="handler.header.conditional.intCondition.greaterThan"></a>handler.header.conditional.intCondition.greaterThan


| Inline definition |
| -------- |
| Uses the argument as a constant value. |

| Property | Type | Description |
| ------- | ------- | ------- |
| fromVar | String | Input variable name. |
| value | int | Value (integer). |

### <a id="handler.header.conditional.intCondition.lessOrEqualTo"></a>handler.header.conditional.intCondition.lessOrEqualTo


| Inline definition |
| -------- |
| Uses the argument as a constant value. |

| Property | Type | Description |
| ------- | ------- | ------- |
| fromVar | String | Input variable name. |
| value | int | Value (integer). |

### <a id="handler.header.conditional.intCondition.lessThan"></a>handler.header.conditional.intCondition.lessThan


| Inline definition |
| -------- |
| Uses the argument as a constant value. |

| Property | Type | Description |
| ------- | ------- | ------- |
| fromVar | String | Input variable name. |
| value | int | Value (integer). |

### <a id="handler.header.conditional.intCondition.notEqualTo"></a>handler.header.conditional.intCondition.notEqualTo


| Inline definition |
| -------- |
| Uses the argument as a constant value. |

| Property | Type | Description |
| ------- | ------- | ------- |
| fromVar | String | Input variable name. |
| value | int | Value (integer). |

### <a id="handler.header.conditional.stringCondition"></a>handler.header.conditional.stringCondition

Condition comparing string in session variable.

| Property | Type | Description |
| ------- | ------- | ------- |
| caseSensitive | boolean | True if the case must match, false if the check is case-insensitive. |
| endsWith | CharSequence | Suffix for the string. |
| equalTo | CharSequence | Literal value the string should match (the same as {@link #value}). |
| fromVar | Object | Variable name. |
| isSet | boolean | Check if the value is set or unset. By default the variable must be set. |
| length | int | Check the length of the string. |
| length (alternative)| [Builder](#handlerheaderconditionalstringconditionlength) | Check the length of the string. |
| matchVar | String | Fetch the value from a variable. |
| negate | boolean | Invert the logic of this condition. Defaults to false. |
| notEqualTo | CharSequence | Value that the string must not match. |
| startsWith | CharSequence | Prefix for the string. |
| value | CharSequence | Literal value the string should match. |

### <a id="handler.header.conditional.stringCondition.length"></a>handler.header.conditional.stringCondition.length

| Property | Type | Description |
| ------- | ------- | ------- |
| equalTo | [Builder](#handlerheaderconditionalstringconditionlengthequalto) | Compared variable must be equal to this value. |
| greaterOrEqualTo | [Builder](#handlerheaderconditionalstringconditionlengthgreaterorequalto) | Compared variable must be greater or equal to this value. |
| greaterThan | [Builder](#handlerheaderconditionalstringconditionlengthgreaterthan) | Compared variable must be greater than this value. |
| lessOrEqualTo | [Builder](#handlerheaderconditionalstringconditionlengthlessorequalto) | Compared variable must be lower or equal to this value. |
| lessThan | [Builder](#handlerheaderconditionalstringconditionlengthlessthan) | Compared variable must be lower than this value. |
| notEqualTo | [Builder](#handlerheaderconditionalstringconditionlengthnotequalto) | Compared variable must not be equal to this value. |

### <a id="handler.header.conditional.stringCondition.length.equalTo"></a>handler.header.conditional.stringCondition.length.equalTo


| Inline definition |
| -------- |
| Uses the argument as a constant value. |

| Property | Type | Description |
| ------- | ------- | ------- |
| fromVar | String | Input variable name. |
| value | int | Value (integer). |

### <a id="handler.header.conditional.stringCondition.length.greaterOrEqualTo"></a>handler.header.conditional.stringCondition.length.greaterOrEqualTo


| Inline definition |
| -------- |
| Uses the argument as a constant value. |

| Property | Type | Description |
| ------- | ------- | ------- |
| fromVar | String | Input variable name. |
| value | int | Value (integer). |

### <a id="handler.header.conditional.stringCondition.length.greaterThan"></a>handler.header.conditional.stringCondition.length.greaterThan


| Inline definition |
| -------- |
| Uses the argument as a constant value. |

| Property | Type | Description |
| ------- | ------- | ------- |
| fromVar | String | Input variable name. |
| value | int | Value (integer). |

### <a id="handler.header.conditional.stringCondition.length.lessOrEqualTo"></a>handler.header.conditional.stringCondition.length.lessOrEqualTo


| Inline definition |
| -------- |
| Uses the argument as a constant value. |

| Property | Type | Description |
| ------- | ------- | ------- |
| fromVar | String | Input variable name. |
| value | int | Value (integer). |

### <a id="handler.header.conditional.stringCondition.length.lessThan"></a>handler.header.conditional.stringCondition.length.lessThan


| Inline definition |
| -------- |
| Uses the argument as a constant value. |

| Property | Type | Description |
| ------- | ------- | ------- |
| fromVar | String | Input variable name. |
| value | int | Value (integer). |

### <a id="handler.header.conditional.stringCondition.length.notEqualTo"></a>handler.header.conditional.stringCondition.length.notEqualTo


| Inline definition |
| -------- |
| Uses the argument as a constant value. |

| Property | Type | Description |
| ------- | ------- | ------- |
| fromVar | String | Input variable name. |
| value | int | Value (integer). |

### <a id="handler.header.filter"></a>handler.header.filter

Compares if the header name matches expression and invokes a processor with the value.

| Property | Type | Description |
| ------- | ------- | ------- |
| header | [Builder](#handlerheaderfilterheader) | Condition on the header name. |
| processor | [Processor.Builder](index.html#processors) | Add one or more processors. |

### <a id="handler.header.filter.header"></a>handler.header.filter.header


| Inline definition |
| -------- |
| String that should be matched. |

| Property | Type | Description |
| ------- | ------- | ------- |
| caseSensitive | boolean | True if the case must match, false if the check is case-insensitive. |
| endsWith | CharSequence | Suffix for the string. |
| equalTo | CharSequence | Literal value the string should match (the same as {@link #value}). |
| length | int | Check the length of the string. |
| length (alternative)| [Builder](#handlerheaderfilterheaderlength) | Check the length of the string. |
| matchVar | String | Fetch the value from a variable. |
| negate | boolean | Invert the logic of this condition. Defaults to false. |
| notEqualTo | CharSequence | Value that the string must not match. |
| startsWith | CharSequence | Prefix for the string. |
| value | CharSequence | Literal value the string should match. |

### <a id="handler.header.filter.header.length"></a>handler.header.filter.header.length

| Property | Type | Description |
| ------- | ------- | ------- |
| equalTo | [Builder](#handlerheaderconditionalstringconditionlengthequalto) | Compared variable must be equal to this value. |
| greaterOrEqualTo | [Builder](#handlerheaderconditionalstringconditionlengthgreaterorequalto) | Compared variable must be greater or equal to this value. |
| greaterThan | [Builder](#handlerheaderconditionalstringconditionlengthgreaterthan) | Compared variable must be greater than this value. |
| lessOrEqualTo | [Builder](#handlerheaderconditionalstringconditionlengthlessorequalto) | Compared variable must be lower or equal to this value. |
| lessThan | [Builder](#handlerheaderconditionalstringconditionlengthlessthan) | Compared variable must be lower than this value. |
| notEqualTo | [Builder](#handlerheaderconditionalstringconditionlengthnotequalto) | Compared variable must not be equal to this value. |

### <a id="handler.header.recordHeaderTime"></a>handler.header.recordHeaderTime

Records alternative metric based on values from a header (e.g. when a proxy reports processing time).

| Property | Type | Description |
| ------- | ------- | ------- |
| header | String | Header carrying the time. |
| metric | String | Name of the created metric. |
| unit | String | Time unit in the header; use either `ms` or `ns`. |

### <a id="handler.rawBytes"></a>handler.rawBytes

Handler processing HTTP response before parsing.

| Property | Type | Description |
| ------- | ------- | ------- |
| transferSizeRecorder | [TransferSizeRecorder.Builder](#handlerrawbytestransfersizerecorder) | Accumulates request and response sizes into custom metrics. |

### <a id="handler.rawBytes.transferSizeRecorder"></a>handler.rawBytes.transferSizeRecorder

Accumulates request and response sizes into custom metrics.

| Property | Type | Description |
| ------- | ------- | ------- |
| key | String | Name of the custom metric for collecting request/response bytes. |

### <a id="handler.status"></a>handler.status

Handle HTTP response status.

| Property | Type | Description |
| ------- | ------- | ------- |
| action | [ActionStatusHandler.Builder](#handlerstatusaction) | Perform certain actions when the status falls into a range. |
| counter | [StatusToCounterHandler.Builder](#handlerstatuscounter) | Counts how many times given status is received. |
| multiplex | [MultiplexStatusHandler.Builder](#handlerstatusmultiplex) | Multiplexes the status based on range into different status handlers. |
| range | [RangeStatusValidator.Builder](#handlerstatusrange) | Marks requests that don't fall into the desired range as invalid. |
| stats | StatusToStatsHandler.Builder | Records number of occurrences of each status counts into custom statistics (these can be displayed in CLI using <code>stats -c</code>). |
| store | [StoreStatusHandler.Builder](#handlerstatusstore) | Stores the status into session variable. |

### <a id="handler.status.action"></a>handler.status.action

Perform certain actions when the status falls into a range.

| Property | Type | Description |
| ------- | ------- | ------- |
| &lt;any&gt; | [Builder](index.html#actions) | Perform a sequence of actions if the range matches. Use range as the key and action in the mapping. Possible values of the status should be separated by commas (,). Ranges can be set using low-high (inclusive) (e.g. 200-299), or replacing lower digits with 'x' (e.g. 2xx). |

### <a id="handler.status.counter"></a>handler.status.counter

Counts how many times given status is received.

| Property | Type | Description |
| ------- | ------- | ------- |
| add | int | Number to be added to the session variable. |
| expectStatus | int | Expected status (others are ignored). All status codes match by default. |
| init | int | Initial value for the session variable. |
| set | int | Do not accumulate (add), just set the variable to this value. |
| var | String | Variable name. |

### <a id="handler.status.multiplex"></a>handler.status.multiplex

Multiplexes the status based on range into different status handlers.

| Property | Type | Description |
| ------- | ------- | ------- |
| &lt;any&gt; | [Builder](#handlerstatusmultiplexany) | Run another handler if the range matches. Use range as the key and another status handler in the mapping. Possible values of the status should be separated by commas (,). Ranges can be set using low-high (inclusive) (e.g. 200-299), or replacing lower digits with 'x' (e.g. 2xx). |

### <a id="handler.status.multiplex.&lt;any&gt;"></a>handler.status.multiplex.&lt;any&gt;

Run another handler if the range matches. Use range as the key and another status handler in the mapping. Possible values of the status should be separated by commas (,). Ranges can be set using low-high (inclusive) (e.g. 200-299), or replacing lower digits with 'x' (e.g. 2xx).

| Property | Type | Description |
| ------- | ------- | ------- |
| action | [ActionStatusHandler.Builder](#handlerstatusaction) | Perform certain actions when the status falls into a range. |
| counter | [StatusToCounterHandler.Builder](#handlerstatuscounter) | Counts how many times given status is received. |
| multiplex | [MultiplexStatusHandler.Builder](#handlerstatusmultiplex) | Multiplexes the status based on range into different status handlers. |
| range | [RangeStatusValidator.Builder](#handlerstatusrange) | Marks requests that don't fall into the desired range as invalid. |
| stats | StatusToStatsHandler.Builder | Records number of occurrences of each status counts into custom statistics (these can be displayed in CLI using <code>stats -c</code>). |
| store | [StoreStatusHandler.Builder](#handlerstatusstore) | Stores the status into session variable. |

### <a id="handler.status.range"></a>handler.status.range

Marks requests that don't fall into the desired range as invalid.


| Inline definition |
| -------- |
| Single status code (<code>204</code>), masked code (<code>2xx</code>) or range (<code>200-399</code>). |

| Property | Type | Description |
| ------- | ------- | ------- |
| max | int | Highest accepted status code. |
| min | int | Lowest accepted status code. |

### <a id="handler.status.store"></a>handler.status.store

Stores the status into session variable.


| Inline definition |
| -------- |
| Variable name. |

| Property | Type | Description |
| ------- | ------- | ------- |
| toVar | Object | Variable name. |

### <a id="HEAD"></a>HEAD

Generic builder for generating a string.


| Inline definition |
| -------- |
| A pattern for <a href="https://hyperfoil.io/userguide/benchmark/variables.html#string-interpolation">string interpolation</a>. |

| Property | Type | Description |
| ------- | ------- | ------- |
| fromVar | Object | Load the string from session variable. |
| pattern | String | Use <a href="https://hyperfoil.io/userguide/benchmark/variables.html#string-interpolation">pattern</a> replacing session variables. |
| value | String | String value used verbatim. |

### <a id="headers"></a>headers

| Property | Type | Description |
| ------- | ------- | ------- |
| &lt;any&gt; | String | Use header name (e.g. <code>Content-Type</code>) as key and value (possibly a <a href="https://hyperfoil.io/userguide/benchmark/variables.html#string-interpolation">pattern</a>). |
| &lt;any&gt; (alternative)| [Builder](#headersany) | Use header name (e.g. <code>Content-Type</code>) as key and specify value in the mapping. |

### <a id="headers.&lt;any&gt;"></a>headers.&lt;any&gt;

Specifies value that should be sent in headers.


| Inline definition |
| -------- |
| The value. This can be a <a href="https://hyperfoil.io/userguide/benchmark/variables.html#string-interpolation">pattern</a>. |

| Property | Type | Description |
| ------- | ------- | ------- |
| fromVar | String | Load header value from session variable. |
| pattern | String | Load header value using a <a href="https://hyperfoil.io/userguide/benchmark/variables.html#string-interpolation">pattern</a>. |

### <a id="metric"></a>metric

Allows categorizing request statistics into metrics based on the request path.

| Property | Type | Description |
| ------- | ------- | ------- |
| &lt;list of strings&gt; | &lt;list of strings&gt; | {::nomarkdown}Allows categorizing request statistics into metrics based on the request path. The expressions are evaluated in the order as provided in the list. Use one of: <ul> <li><code>regexp -&gt; replacement</code>, e.g. <code>([^?]*)(\?.*)? -&gt; $1</code> to drop the query part. <li><code>regexp</code> (don't do any replaces and use the full path), e.g. <code>.*.jpg</code> <li><code>-&gt; name</code> (metric applied if none of the previous expressions match). </ul>{:/} |

### <a id="OPTIONS"></a>OPTIONS

Generic builder for generating a string.


| Inline definition |
| -------- |
| A pattern for <a href="https://hyperfoil.io/userguide/benchmark/variables.html#string-interpolation">string interpolation</a>. |

| Property | Type | Description |
| ------- | ------- | ------- |
| fromVar | Object | Load the string from session variable. |
| pattern | String | Use <a href="https://hyperfoil.io/userguide/benchmark/variables.html#string-interpolation">pattern</a> replacing session variables. |
| value | String | String value used verbatim. |

### <a id="PATCH"></a>PATCH

Generic builder for generating a string.


| Inline definition |
| -------- |
| A pattern for <a href="https://hyperfoil.io/userguide/benchmark/variables.html#string-interpolation">string interpolation</a>. |

| Property | Type | Description |
| ------- | ------- | ------- |
| fromVar | Object | Load the string from session variable. |
| pattern | String | Use <a href="https://hyperfoil.io/userguide/benchmark/variables.html#string-interpolation">pattern</a> replacing session variables. |
| value | String | String value used verbatim. |

### <a id="path"></a>path

Generic builder for generating a string.


| Inline definition |
| -------- |
| A pattern for <a href="https://hyperfoil.io/userguide/benchmark/variables.html#string-interpolation">string interpolation</a>. |

| Property | Type | Description |
| ------- | ------- | ------- |
| fromVar | Object | Load the string from session variable. |
| pattern | String | Use <a href="https://hyperfoil.io/userguide/benchmark/variables.html#string-interpolation">pattern</a> replacing session variables. |
| value | String | String value used verbatim. |

### <a id="POST"></a>POST

Generic builder for generating a string.


| Inline definition |
| -------- |
| A pattern for <a href="https://hyperfoil.io/userguide/benchmark/variables.html#string-interpolation">string interpolation</a>. |

| Property | Type | Description |
| ------- | ------- | ------- |
| fromVar | Object | Load the string from session variable. |
| pattern | String | Use <a href="https://hyperfoil.io/userguide/benchmark/variables.html#string-interpolation">pattern</a> replacing session variables. |
| value | String | String value used verbatim. |

### <a id="PUT"></a>PUT

Generic builder for generating a string.


| Inline definition |
| -------- |
| A pattern for <a href="https://hyperfoil.io/userguide/benchmark/variables.html#string-interpolation">string interpolation</a>. |

| Property | Type | Description |
| ------- | ------- | ------- |
| fromVar | Object | Load the string from session variable. |
| pattern | String | Use <a href="https://hyperfoil.io/userguide/benchmark/variables.html#string-interpolation">pattern</a> replacing session variables. |
| value | String | String value used verbatim. |

### <a id="sla"></a>sla

Defines a list of Service Level Agreements (SLAs) - conditions that must hold for benchmark to be deemed successful.

| Property | Type | Description |
| ------- | ------- | ------- |
| &lt;list of mappings&gt; | [&lt;list of builders&gt;](#slalist-of-mappings) | One or more SLA configurations. |

### <a id="sla.&lt;list of mappings&gt;"></a>sla.&lt;list of mappings&gt;

Defines a Service Level Agreement (SLA) - conditions that must hold for benchmark to be deemed successful.

| Property | Type | Description |
| ------- | ------- | ------- |
| blockedRatio | double | Maximum allowed ratio of time spent waiting for usable connection to sum of response latencies and blocked time. Default is 0 - client must not be blocked. Set to 1 if the client can block without limits. |
| errorRatio | double | Maximum allowed ratio of errors: connection failures or resets, timeouts and internal errors. Valid values are 0.0 - 1.0 (inclusive). Note: 4xx and 5xx statuses are NOT considered errors for this SLA parameter. Use <code>invalidRatio</code> for that. |
| invalidRatio | double | Maximum allowed ratio of requests with responses marked as invalid. Valid values are 0.0 - 1.0 (inclusive). Note: With default settings 4xx and 5xx statuses are considered invalid. Check out <code>ergonomics.autoRangeCheck</code> or <code>httpRequest.handler.autoRangeCheck</code> to change this. |
| limits | [Builder](#slalist-of-mappingslimits) | Percentile limits. |
| meanResponseTime | String | Maximum allowed mean (average) response time. Use suffix `ns`, `us`, `ms` or `s` to specify units. |
| window | String | Period over which the stats should be collected. By default the SLA applies to stats from whole phase. |

### <a id="sla.&lt;list of mappings&gt;.limits"></a>sla.&lt;list of mappings&gt;.limits

Percentile limits.

| Property | Type | Description |
| ------- | ------- | ------- |
| &lt;any&gt; | String | Use percentile (value between 0.0 and 1.0) as key and response time with unit (e.g. `ms`) in suffix as value. |

### <a id="TRACE"></a>TRACE

Generic builder for generating a string.


| Inline definition |
| -------- |
| A pattern for <a href="https://hyperfoil.io/userguide/benchmark/variables.html#string-interpolation">string interpolation</a>. |

| Property | Type | Description |
| ------- | ------- | ------- |
| fromVar | Object | Load the string from session variable. |
| pattern | String | Use <a href="https://hyperfoil.io/userguide/benchmark/variables.html#string-interpolation">pattern</a> replacing session variables. |
| value | String | String value used verbatim. |

