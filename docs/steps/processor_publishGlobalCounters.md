---
---
# publishGlobalCounters

Gathers values from session variables and publishes them globally (to all agents). You can name the counters individually (example 1) or use the variable names (example 2): <br> <code> # Example 1: - publishGlobalCounters: key: myKey vars: [ foo, bar ] # Example 2: - publishGlobalCounters: key: someOtherKey vars: - foo: myFoo - bar: bbb </code>

| Property | Type | Description |
| ------- | ------- | -------- |
| key | String | Identifier of the global record. |
| vars | [Builder](#vars) | List of names and session variables. |

### <a id="vars"></a>vars

| Property | Type | Description |
| ------- | ------- | ------- |
| &lt;any&gt; | &lt;unknown&gt; | <font color="#606060">&lt;no description&gt;</font> |
| &lt;list of strings&gt; | &lt;unknown&gt; | <font color="#606060">&lt;no description&gt;</font> |

