# 获取指定的Job<a name="cce_02_0160"></a>

## 功能介绍<a name="section34495516"></a>

This API is used to read the specified Job.

## URI<a name="section42024188"></a>

GET /apis/batch/v1/namespaces/\{namespace\}/jobs/\{name\}

[表1](#d0e41471)描述该API的参数。

**表 1**  参数解释

<a name="d0e41471"></a>
<table><thead align="left"><tr id="row14497772"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.1"><p id="p65652297517"><a name="p65652297517"></a><a name="p65652297517"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30.303030303030305%" id="mcps1.2.4.1.2"><p id="p165661629135114"><a name="p165661629135114"></a><a name="p165661629135114"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="36.36363636363636%" id="mcps1.2.4.1.3"><p id="p14567629115114"><a name="p14567629115114"></a><a name="p14567629115114"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row66636327"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p28833370"><a name="p28833370"></a><a name="p28833370"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p53801671"><a name="p53801671"></a><a name="p53801671"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="36.36363636363636%" headers="mcps1.2.4.1.3 "><p id="p62968084"><a name="p62968084"></a><a name="p62968084"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="row29841846"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p1270455"><a name="p1270455"></a><a name="p1270455"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p35797996"><a name="p35797996"></a><a name="p35797996"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="36.36363636363636%" headers="mcps1.2.4.1.3 "><p id="p13956541"><a name="p13956541"></a><a name="p13956541"></a>Object name and auth scope, such as for teams and projects.</p>
</td>
</tr>
<tr id="row58500012"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p40880564"><a name="p40880564"></a><a name="p40880564"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p22991372"><a name="p22991372"></a><a name="p22991372"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="36.36363636363636%" headers="mcps1.2.4.1.3 "><p id="p50361820"><a name="p50361820"></a><a name="p50361820"></a>Name of the Job.</p>
</td>
</tr>
<tr id="row50603201"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p5218617"><a name="p5218617"></a><a name="p5218617"></a>exact</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p20054846"><a name="p20054846"></a><a name="p20054846"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="36.36363636363636%" headers="mcps1.2.4.1.3 "><p id="p13829815"><a name="p13829815"></a><a name="p13829815"></a>Should the export be exact. Exact export maintains cluster-specific fields like 'Namespace'.</p>
</td>
</tr>
<tr id="row57359475"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p15605878"><a name="p15605878"></a><a name="p15605878"></a>export</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p56116577"><a name="p56116577"></a><a name="p56116577"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="36.36363636363636%" headers="mcps1.2.4.1.3 "><p id="p49148893"><a name="p49148893"></a><a name="p49148893"></a>Should this value be exported. Export strips fields that a user cannot specify.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="section42673379"></a>

N/A

## 响应消息<a name="section48516097"></a>

**响应参数：**

响应参数的详细描述请参见[表2](创建Job.md#table8040885)。

**响应示例：**

```
{
    "kind": "Job",
    "apiVersion": "batch/v1",
    "metadata": {
        "name": "example-job",
        "namespace": "default",
        "selfLink": "/apis/batch/v1/namespaces/default/jobs/example-job",
        "uid": "d93a3569-a2be-11e6-a008-fa043d458cc7",
        "resourceVersion": "7482",
        "creationTimestamp": "2016-11-04T18:45:25Z"
    },
    "spec": {
        "parallelism": 1,
        "completions": 1,
        "selector": {
            "matchLabels": {
                "controller-uid": "d93a3569-a2be-11e6-a008-fa043d458cc7"
            }
        },
        "template": {
            "metadata": {
                "name": "example-job",
                "creationTimestamp": null,
                "labels": {
                    "controller-uid": "d93a3569-a2be-11e6-a008-fa043d458cc7",
                    "job-name": "example-job"
                }
            },
            "spec": {
                "containers": [
                    {
                        "name": "pi",
                        "image": "perl",
                        "command": [
                            "perl",
                            "-Mbignum=bpi",
                            "-wle",
                            "print bpi(2000)"
                        ],
                        "resources": {},
                        "terminationMessagePath": "/dev/termination-log",
                        "imagePullPolicy": "Always"
                    }
                ],
                "restartPolicy": "Never",
                "terminationGracePeriodSeconds": 30,
                "dnsPolicy": "ClusterFirst",
                "securityContext": {}
            }
        }
    },
    "status": {
        "startTime": "2016-11-04T18:45:25Z",
        "active": 1
    }
}
```

## 状态码<a name="section33991695"></a>

[表2](#d0e41570)描述API的状态码。

**表 2**  状态码

<a name="d0e41570"></a>
<table><thead align="left"><tr id="row22801529"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p34984551"><a name="p34984551"></a><a name="p34984551"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p15176386"><a name="p15176386"></a><a name="p15176386"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row21327729"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p49824477"><a name="p49824477"></a><a name="p49824477"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p9250797"><a name="p9250797"></a><a name="p9250797"></a>This operation succeeds, and a Job resource object is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

