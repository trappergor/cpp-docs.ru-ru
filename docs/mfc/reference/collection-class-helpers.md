---
title: "Вспомогательные функции классов коллекции | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.mfc.macros.classes
dev_langs: C++
helpviewer_keywords:
- DestructElements function
- ConstructElements function
- SerializeElements function
- collection classes [MFC], helper functions
- helper functions collection class [MFC]
ms.assetid: bc3a2368-9edd-4748-9e6a-13cba79517ca
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 82b11c4cbe8f862121d89c308ab11d53582931d7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="collection-class-helpers"></a>Вспомогательные функции классов коллекции
Классы коллекций `CMap`, `CList`, и `CArray` использовать Шаблонизированный вспомогательный объект глобальные функции для таких целей, как сравнение, копирования и сериализации элементов. Как часть реализации классов на основе `CMap`, `CList`, и `CArray`, необходимо переопределить эти функции, при необходимости с версиями, специально созданных для типа данных, хранящихся в вашей карты, список или массив. Сведения о переопределении вспомогательные функции, такие как `SerializeElements`, см. в статье [коллекций: как создать типобезопасную коллекцию](../../mfc/how-to-make-a-type-safe-collection.md). Обратите внимание, что **ConstructElements** и **DestructElements** являются устаревшими.  
  
 Библиотеки классов Microsoft Foundation предоставляет следующие глобальные функции в afxtempl.h могут помочь настроить пользовательские классы коллекций:  
  
### <a name="collection-class-helpers"></a>Вспомогательные функции классов коллекции  
  
|||  
|-|-|  
|[CompareElements](#compareelements)|Указывает, совпадают ли элементы.|  
|[CopyElements](#copyelements)|Копирует элементы из одного массива в другой.|  
|[DumpElements](#dumpelements)|Предоставляет поточно ориентированный вывод диагностических сообщений.|  
|[HashKey](#hashkey)|Вычисляет хэш-ключа.|  
|[SerializeElements](#serializeelements)|Сохраняет или получает элементы в или из архива.|  
  
##  <a name="compareelements"></a>CompareElements  
 Вызывается непосредственно [CList::Find] (#clist__find clist class.md #not_found.md и косвенно посредством [cmap__lookup](cmap-class.md#lookup) и [cmap__operator &#91; &#93;](cmap-class.md#operator_at).  
  
```   
template<class TYPE, class ARG_TYPE>  
BOOL AFXAPI  
CompareElements(
    const TYPE* pElement1,  
    const ARG_TYPE* pElement2);  
```  
  
### <a name="parameters"></a>Параметры  
 *ТИП*  
 Тип первого элемента для сравнения.  
  
 `pElement1`  
 Указатель на первый элемент для сравнения.  
  
 `ARG_TYPE`  
 Тип второго элемента для сравнения.  
  
 `pElement2`  
 Указатель на второй элемент для сравнения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если объект, на который указывает `pElement1` равен объекту, на который указывает `pElement2`; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 `CMap` Вызывает использование `CMap` параметров шаблона *ключ* и `ARG_KEY`.  
  
 Реализация по умолчанию возвращает результат сравнения объектов  *\*pElement1* и  *\*pElement2*. Переопределите эту функцию, чтобы он сравнивает элементы в виде, наиболее подходящий для вашего приложения.  
  
 В языке C++ определен оператор сравнения ( `==`) для простых типов ( `char`, `int`, **float**и так далее), но не определяет оператор сравнения для классов и структур. Если вы хотите использовать `CompareElements` или для создания экземпляра одного из классов коллекций, которые он использует, необходимо определить оператор сравнения или перегрузку `CompareElements` с версией, которая возвращает соответствующие значения.  
  
### <a name="requirements"></a>Требования  
   **Заголовок:** afxtempl.h   
  
##  <a name="copyelements"></a>CopyElements  
 Эта функция вызывается напрямую с помощью [CArray::Append](carray-class.md#append) и [CArray::Copy](carray-class.md#copy).  
  
```   
template<class TYPE>  
void AFXAPI CopyElements(
    TYPE* pDest,  
    const TYPE* pSrc,  
    INT_PTR nCount);  
```  
  
### <a name="parameters"></a>Параметры  
 *ТИП*  
 Параметр шаблона, указывающий тип элементов для копирования.  
  
 `pDest`  
 Указатель в место назначения, куда будут скопированы элементы.  
  
 `pSrc`  
 Указатель на источник копируемых элементов.  
  
 `nCount`  
 Число копируемых элементов.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию использует простой оператор присваивания (  **=**  ) для выполнения операции копирования. Если при копировании типа нет перегруженного оператора =, реализация по умолчанию выполняет побитовое копирование.  
  
 Сведения о реализации это и другие вспомогательные функции, см. в статье [коллекций: как создать типобезопасную коллекцию](../how-to-make-a-type-safe-collection.md).  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxtempl.h  
  
##  <a name="dumpelements"></a>DumpElements  
 Предоставляет поточно ориентированный диагностические данные в виде текста для элементов коллекции переопределение.  
  
```   
template<class TYPE>  
void  AFXAPI DumpElements(
    CDumpContext& dc,  
    const TYPE* pElements,  
    INT_PTR nCount);  
```  
  
### <a name="parameters"></a>Параметры  
 `dc`  
 Дампа контекст для записи элементов в дамп.  
  
 *ТИП*  
 Параметр шаблона, определяющий тип элементов.  
  
 `pElements`  
 Указатель элементов дамп.  
  
 `nCount`  
 Число элементов в дамп.  
  
### <a name="remarks"></a>Примечания  
 **CArray::Dump**, **CList::Dump**, и **CMap::Dump** функции вызывать его, если глубина дампа больше 0.  
  
 Реализация по умолчанию не выполняет никаких действий. Если элементами коллекции являются производными от `CObject`, переопределенный обычно перебора элементов коллекции, вызов `Dump` для каждого элемента, в свою очередь.  
  

### <a name="requirements"></a>Требования  
  **Заголовок** afxtempl.h  
  
##  <a name="hashkey"></a>HashKey  
 Вычисляет хэш-значение для указанного ключа.  
  
```  
template<class ARG_KEY>  
AFX_INLINE UINT AFXAPI HashKey(ARG_KEY  key); 
```  
  
### <a name="parameters"></a>Параметры  
 `ARG_KEY`  
 Параметр шаблона, указывающий тип данных, используемый для доступа к ключам карты.  
  
 `key`  
 Ключ, значение которого хэш вычисляться.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Хэш-значение ключа.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается напрямую с помощью [CMap::RemoveKey](cmap-class.md#removekey) и косвенно посредством [CMap::Lookup](cmap-class.md#lookup) и [CMap::Operator &#91; &#93;](cmap-class.md#operator_at).
  
 Реализация по умолчанию создает хэш-значения путем перехода `key` вправо на четыре позиции. Переопределите эту функцию, чтобы он возвращал хэш-значения подходящий для вашего приложения.  
  
### <a name="example"></a>Пример
 ```cpp  
template <> UINT AFXAPI HashKey(unsigned __int64 key)
{
   // Generate the hash value by XORing the lower 32 bits of the number 
   // with the upper 32 bits
   return(UINT(key) ^ UINT(key >> 32));
}
 ```
 
### <a name="requirements"></a>Требования  
  **Заголовок** afxtempl.h 
  
##  <a name="serializeelements"></a>SerializeElements  
 [CArray](carray-class.md), [CList](clist-class.md), и [CMap](cmap-class.md) эта функция вызывается для сериализации элементов.  
  
```   
template<class TYPE>  
void AFXAPI SerializeElements(CArchive& ar, TYPE* pElements, INT_PTR nCount);  
```  
  
### <a name="parameters"></a>Параметры  
 *ТИП*  
 Параметр шаблона, определяющий тип элементов.  
  
 `ar`  
 Для архивации в архив объекта.  
  
 `pElements`  
 Указатель элементов архивации.  
  
 `nCount`  
 Количество элементов архивации  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию не побитовой операции чтения или записи.  
  
 Сведения о реализации это и другие вспомогательные функции, см. в статье [коллекций: как создать типобезопасную коллекцию](../how-to-make-a-type-safe-collection.md).  
  
### <a name="example"></a>Пример  
 См. пример в статье [коллекций: как создать типобезопасную коллекцию](../how-to-make-a-type-safe-collection.md).  
 
### <a name="requirements"></a>Требования  
  **Заголовок** afxtempl.h 
    
## <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](mfc-macros-and-globals.md)   
 [Класс CMap](cmap-class.md)   
 [CList-класс](clist-class.md)   
 [Класс CArray](carray-class.md)