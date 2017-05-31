# OpenAPI Config Extension Specification

#### Version 0.1.0-rc1

## Introduction

The OpenAPI Config Specification (OACXS) is a project to describe an [extension](https://github.com/OAI/OpenAPI-Specification/blob/OpenAPI.next/versions/3.0.md#specificationExtensions) to the OpenAPI Specification (OAS) for application configuration objects.

#### <a name="configObject"></a>Config Object

Describes an API's global config object.

##### Fixed Fields

Field Name | Type | Description
---|:---:|---
<a name="x-config"></a>x-config | [[Config Parameter Object](#configParameterObject) \| [Reference Object](https://github.com/OAI/OpenAPI-Specification/blob/OpenAPI.next/versions/3.0.md#referenceObject)] | A list of parameters that are applicable for this configuration. If a parameter is already defined at the [Config Object](#xConfigObject), the new definition will override it but can never remove it. The list MUST NOT include duplicated parameters. The list can use the [Reference Object](https://github.com/OAI/OpenAPI-Specification/blob/OpenAPI.next/versions/3.0.md#referenceObject) to link to parameters that are defined at the [OpenAPI Object's components/x-config](#componentsXConfig).

#### <a name="configParameterObject"></a>Config Parameter Object

Describes a single config parameter.

##### Fixed Fields

Field Name | Type | Description
---|:---:|---
<a name="parameterName"></a>name | `string` | **Required.** The name of the parameter. Parameter names are *case sensitive*.
<a name="parameterDescription"></a>description | `string` | A brief description of the parameter. This could contain examples of use.  [CommonMark syntax](http://spec.commonmark.org/) can be used for rich text representation.
<a name="parameterRequired"></a>required | `boolean` | Determines whether this parameter is mandatory. The default value is `false`.
<a name="parameterDeprecated"></a> deprecated | `boolean` | Specifies that a parameter is deprecated and SHOULD be transitioned out of usage.

A [`schema`](https://github.com/OAI/OpenAPI-Specification/blob/OpenAPI.next/versions/3.0.md#parameterSchema) can be used to describe the structure and syntax of the config parameter.

Field Name | Type | Description
---|:---:|---
<a name="parameterSchema"></a>schema | [Schema Object](https://github.com/OAI/OpenAPI-Specification/blob/OpenAPI.next/versions/3.0.md#schemaObject) \| [Reference Object](https://github.com/OAI/OpenAPI-Specification/blob/OpenAPI.next/versions/3.0.md#referenceObject) | The schema defining the type used for the parameter.
