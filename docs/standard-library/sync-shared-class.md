---
title: sync_shared 类
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::sync_shared
- allocators/stdext::sync_shared::allocate
- allocators/stdext::sync_shared::deallocate
- allocators/stdext::sync_shared::equals
helpviewer_keywords:
- stdext::sync_shared
- stdext::sync_shared [C++], allocate
- stdext::sync_shared [C++], deallocate
- stdext::sync_shared [C++], equals
ms.assetid: cab3af9e-3d1a-4f2c-8580-0f89e5687d8e
ms.openlocfilehash: c368e99eb9f128963e90cdc1d39bdb9d4569efe9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "50483377"
---
# <a name="syncshared-class"></a>sync_shared 类

介绍[同步筛选器](../standard-library/allocators-header.md)，它使用互斥体来控制对所有分配器共享的缓存对象的访问。

## <a name="syntax"></a>语法

```cpp
template <class Cache>
class sync_shared
```

### <a name="parameters"></a>参数

|参数|描述|
|---------------|-----------------|
|*缓存*|与同步筛选器相关联的缓存类型。 它可以是 [cache_chunklist](../standard-library/cache-chunklist-class.md)、[cache_freelist](../standard-library/cache-freelist-class.md) 或 [cache_suballoc](../standard-library/cache-suballoc-class.md)。|

### <a name="member-functions"></a>成员函数

|成员函数|描述|
|-|-|
|[allocate](#allocate)|分配内存块。|
|[deallocate](#deallocate)|从指定位置开始从存储中释放指定数量的的对象。|
|[equals](#equals)|比较两个缓存是否相等。|

## <a name="requirements"></a>要求

**标头：**\<allocators>

**命名空间：** stdext

## <a name="allocate"></a>  sync_shared::allocate

分配内存块。

```cpp
void *allocate(std::size_t count);
```

### <a name="parameters"></a>参数

|参数|描述|
|---------------|-----------------|
|*count*|数组中要分配的元素数目。|

### <a name="return-value"></a>返回值

指向已分配对象的指针。

### <a name="remarks"></a>备注

成员函数会锁定互斥体，调用 `cache.allocate(count)`、解除对互斥体的锁定并返回之前调用 `cache.allocate(count)` 的结果。 `cache` 表示当前缓存对象。

## <a name="deallocate"></a>  sync_shared::deallocate

从指定位置开始从存储中释放指定数量的的对象。

```cpp
void deallocate(void* ptr, std::size_t count);
```

### <a name="parameters"></a>参数

|参数|描述|
|---------------|-----------------|
|*ptr*|指向要从存储中释放的第一个对象的指针。|
|*count*|要从存储中释放的对象数量。|

### <a name="remarks"></a>备注

此成员函数会锁定互斥体，调用 `cache.deallocate(ptr, count)`其中 `cache` 表示缓存对象），然后取消对该互斥体的锁定。

## <a name="equals"></a>  sync_shared::equals

比较两个缓存是否相等。

```cpp
bool equals(const sync_shared<Cache>& Other) const;
```

### <a name="parameters"></a>参数

|参数|描述|
|---------------|-----------------|
|*缓存*|与同步筛选器相关联的缓存类型。|
|*其他*|要比较是否相等的缓存。|

### <a name="return-value"></a>返回值

**true**如果的结果`cache.equals(Other.cache)`，其中`cache`表示缓存对象，则不**true**; 否则为**false**。

### <a name="remarks"></a>备注

## <a name="see-also"></a>请参阅

[\<allocators>](../standard-library/allocators-header.md)<br/>
