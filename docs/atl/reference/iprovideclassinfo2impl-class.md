---
title: IProvideClassInfo2Impl 类
ms.date: 11/04/2016
f1_keywords:
- IProvideClassInfo2Impl
- ATLCOM/ATL::IProvideClassInfo2Impl
- ATLCOM/ATL::IProvideClassInfo2Impl::IProvideClassInfo2Impl
- ATLCOM/ATL::IProvideClassInfo2Impl::GetClassInfo
- ATLCOM/ATL::IProvideClassInfo2Impl::GetGUID
- ATLCOM/ATL::IProvideClassInfo2Impl::_tih
helpviewer_keywords:
- IProvideClassInfo2Impl class
- IProvideClassInfo2 ATL implementation
- class information, ATL
ms.assetid: d74956e8-9c69-4cba-b99d-ca1ac031bb9d
ms.openlocfilehash: a270efa5daac8c8b608f05bdb752195f806b7935
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "50539641"
---
# <a name="iprovideclassinfo2impl-class"></a>IProvideClassInfo2Impl 类

此类提供的默认实现[IProvideClassInfo](/windows/desktop/api/ocidl/nn-ocidl-iprovideclassinfo)并[IProvideClassInfo2](/windows/desktop/api/ocidl/nn-ocidl-iprovideclassinfo2)方法。

## <a name="syntax"></a>语法

```
template <const CLSID* pcoclsid,
    const IID* psrcid,
    const GUID* plibid = &CAtlModule::m_libid,
    WORD wMajor = 1,
    WORD wMinor = 0, class tihclass = CComTypeInfoHolder>
class ATL_NO_VTABLE IProvideClassInfo2Impl : public IProvideClassInfo2
```

#### <a name="parameters"></a>参数

*pcoclsid*<br/>
一个指向组件类的标识符。

*psrcid*<br/>
一个指向用于 coclass 的默认传出调度接口的标识符。

*plibid*<br/>
一个指向包含有关接口的信息的类型库的 LIBID。 默认情况下，传递服务器级类型库。

*wMajor*<br/>
类型库的主版本。 默认值为 1。

*wMinor*<br/>
类型库的次版本。 默认值为 0。

*tihclass*<br/>
用于管理组件类的类型信息的类。 默认值为 `CComTypeInfoHolder`。

## <a name="members"></a>成员

### <a name="constructors"></a>构造函数

|name|描述|
|----------|-----------------|
|[IProvideClassInfo2Impl::IProvideClassInfo2Impl](#iprovideclassinfo2impl)|构造函数。|

### <a name="public-methods"></a>公共方法

|名称|描述|
|----------|-----------------|
|[IProvideClassInfo2Impl::GetClassInfo](#getclassinfo)|检索`ITypeInfo`组件类的类型信息的指针。|
|[IProvideClassInfo2Impl::GetGUID](#getguid)|检索对象的传出调度接口的 GUID。|

### <a name="protected-data-members"></a>受保护的数据成员

|name|描述|
|----------|-----------------|
|[IProvideClassInfo2Impl::_tih](#_tih)|管理用于 coclass 的类型信息。|

## <a name="remarks"></a>备注

[IProvideClassInfo2](/windows/desktop/api/ocidl/nn-ocidl-iprovideclassinfo2)接口扩展[IProvideClassInfo](/windows/desktop/api/ocidl/nn-ocidl-iprovideclassinfo)通过添加`GetGUID`方法。 此方法允许客户端检索对象的输出接口 IID 为其默认事件集。 类`IProvideClassInfo2Impl`提供的默认实现`IProvideClassInfo`和`IProvideClassInfo2`方法。

`IProvideClassInfo2Impl` 包含类型的静态成员`CComTypeInfoHolder`管理用于 coclass 的类型信息。

## <a name="inheritance-hierarchy"></a>继承层次结构

`IProvideClassInfo2`

`IProvideClassInfo2Impl`

## <a name="requirements"></a>要求

**标头：** atlcom.h

##  <a name="getclassinfo"></a>  IProvideClassInfo2Impl::GetClassInfo

检索`ITypeInfo`组件类的类型信息的指针。

```
STDMETHOD(GetClassInfo)(ITypeInfo** pptinfo);
```

### <a name="remarks"></a>备注

请参阅[IProvideClassInfo::GetClassInfo](/windows/desktop/api/ocidl/nf-ocidl-iprovideclassinfo-getclassinfo) Windows SDK 中。

##  <a name="getguid"></a>  IProvideClassInfo2Impl::GetGUID

检索对象的传出调度接口的 GUID。

```
STDMETHOD(GetGUID)(
    DWORD dwGuidKind,
    GUID* pGUID);
```

### <a name="remarks"></a>备注

请参阅[IProvideClassInfo2::GetGUID](/windows/desktop/api/ocidl/nf-ocidl-iprovideclassinfo2-getguid) Windows SDK 中。

##  <a name="iprovideclassinfo2impl"></a>  IProvideClassInfo2Impl::IProvideClassInfo2Impl

构造函数。

```
IProvideClassInfo2Impl();
```

### <a name="remarks"></a>备注

调用`AddRef`上[_tih](#_tih)成员。 析构函数调用 `Release`。

##  <a name="_tih"></a>  IProvideClassInfo2Impl::_tih

此静态数据成员是类模板参数的实例*tihclass*，默认情况下是`CComTypeInfoHolder`。

```
static  tihclass
    _tih;
```

### <a name="remarks"></a>备注

`_tih` 管理用于 coclass 的类型信息。

## <a name="see-also"></a>请参阅

[类概述](../../atl/atl-class-overview.md)
