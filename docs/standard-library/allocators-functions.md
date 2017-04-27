---
title: "Макросы &lt;распределителей&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- allocators/std::ALLOCATOR_DECL
- allocators/std::CACHE_CHUNKLIST
- allocators/std::CACHE_FREELIST
- allocators/std::CACHE_SUBALLOC
- allocators/std::SYNC_DEFAULT
ms.assetid: 9cb5ee07-1ff9-4594-ae32-3c8c6efb511a
caps.latest.revision: 12
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: da17f9af1f14df13eb3871ef9ccf785356e02de4
ms.openlocfilehash: abc1dd29ba68540a6669f7aff1bbd3dffdab616a
ms.lasthandoff: 02/24/2017

---
# <a name="ltallocatorsgt-macros"></a>Макросы &lt;распределителей&gt;
||||  
|-|-|-|  
|[ALLOCATOR_DECL](#allocator_decl)|[CACHE_CHUNKLIST](#cache_chunklist)|[CACHE_FREELIST](#cache_freelist)|  
|[CACHE_SUBALLOC](#cache_suballoc)|[SYNC_DEFAULT](#sync_default)|  
  
##  <a name="allocator_decl"></a>  ALLOCATOR_DECL  
 Создает класс шаблона распределителя.  
  
```
#define ALLOCATOR_DECL(cache, sync, name) <alloc_template>
```  
  
### <a name="remarks"></a>Примечания  
 Макрос создает определение шаблона `template <class Type> class name {.....}` и специализацию `template <> class name<void> {.....}`, которые вместе определяют шаблон класс распределителя, использующий фильтр синхронизации `sync` и кэш типа `cache`.  
  
 Для компиляторов, которые могут компилировать повторную привязку, итоговое определение шаблона выглядит следующим образом:  
```  
struct rebind
   {    /* convert a name<Type> to a name<Other> */
   typedef name<Other> other;
   };  
 ```  
 Для компиляторов, которые не могут компилировать повторную привязку, итоговое определение шаблона выглядит следующим образом:  
  
```
template <class Type<class name
    : public stdext::allocators::allocator_base<Type,
    sync<stdext::allocators::rts_alloc<cache>>>
{
public:
    name() {}
    template <class Other>
    name(const name<Other>&) {}
    template <class Other>
    name& operator= (const name<Other>&)
    {
        return *this;
    }
};
```  
  
##  <a name="cache_chunklist"></a>  CACHE_CHUNKLIST  
 Создает `stdext::allocators::cache_chunklist<sizeof(Type)>`.  
  
```
#define CACHE_CHUNKLIST <cache_class>
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="cache_freelist"></a>  CACHE_FREELIST  
 Создает `stdext::allocators::cache_freelist<sizeof(Type), max>`.  
  
```
#define CACHE_FREELIST(max) <cache_class>
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="cache_suballoc"></a>  CACHE_SUBALLOC  
 Создает `stdext::allocators::cache_suballoc<sizeof(Type)>`.  
  
```
#define CACHE_SUBALLOC <cache_class>
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="sync_default"></a>  SYNC_DEFAULT  
 Создает фильтр синхронизации.  
  
```
#define SYNC_DEFAULT <sync_template>
```  
  
### <a name="remarks"></a>Примечания  
 Если компилятор поддерживает компиляцию как однопоточных, так и многопоточных приложений, для однопоточных приложений макрос создает `stdext::allocators::sync_none`; для всех остальных случаев он создает `stdext::allocators::sync_shared`.  
  
## <a name="see-also"></a>См. также  
 [\<allocators>](../standard-library/allocators-header.md)





