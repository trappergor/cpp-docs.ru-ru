---
title: "Вспомогательные функции классов коллекции | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros.classes
dev_langs:
- C++
helpviewer_keywords:
- DestructElements function
- ConstructElements function
- SerializeElements function
- collection classes, helper functions
- helper functions collection class
ms.assetid: bc3a2368-9edd-4748-9e6a-13cba79517ca
caps.latest.revision: 14
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: d2649ef9c8b0320a94ec28a2341baa0f768b07d0
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="collection-class-helpers"></a>Вспомогательные функции классов коллекции
Классы коллекций `CMap`, `CList`, и `CArray` использовать шаблонные глобального вспомогательные функции для таких целей, как сравнение, копирования и сериализации элементов. Как часть своей реализации классов на основе `CMap`, `CList`, и `CArray`, необходимо переопределить эти функции при необходимости с версиями, которые соответствуют типу данных, хранящихся в вашей карты, список или массив. Сведения о переопределении вспомогательные функции, такие как `SerializeElements`, см. в статье [коллекций: осуществление строго типизированную коллекцию](../../mfc/how-to-make-a-type-safe-collection.md). Обратите внимание, что **ConstructElements** и **DestructElements** являются устаревшими.  
  
 Библиотеки классов Microsoft Foundation предоставляет следующие глобальные функции в afxtempl.h помогают настроить пользовательские классы коллекций:  
  
### <a name="collection-class-helpers"></a>Вспомогательные функции классов коллекции  
  
|||  
|-|-|  
|[CompareElements](#compareelements)|Указывает, совпадают ли элементы.|  
|[CopyElements](#copyelements)|Копирует элементы из одного массива в другой.|  
|[DumpElements](#dumpelements)|Предоставляет поточно ориентированный выходных данных диагностики.|  
|[HashKey](#hashkey)|Вычисляет хэш-ключа.|  
|[SerializeElements](#serializeelements)|Сохраняет или получает элементы в или из архива.|  
  
##  <a name="compareelements"></a>CompareElements  
 Напрямую с именем [CList::Find] (#clist__find clist class.md #not_found.md и косвенно [cmap__lookup](cmap-class.md#lookup) и [[cmap__operator]](cmap-class.md#operator_at).  
  
```   
template<class TYPE, class ARG_TYPE>  
BOOL AFXAPI  
CompareElements(
    const TYPE* pElement1,  
    const ARG_TYPE* pElement2);  
```  
  
### <a name="parameters"></a>Параметры  
 *ТИП*  
 Тип первый элемент для сравнения.  
  
 `pElement1`  
 Указатель на первый элемент для сравнения.  
  
 `ARG_TYPE`  
 Тип второй элемент для сравнения.  
  
 `pElement2`  
 Указатель на второй элемент для сравнения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если объект, на который указывает `pElement1` равен объекту, на который указывает `pElement2`; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 `CMap` Вызывает использование `CMap` параметры шаблона *ключ* и `ARG_KEY`.  
  
 Реализация по умолчанию возвращает результат сравнения * \*pElement1* и * \*pElement2*. Эту функцию можно переопределите, чтобы он сравнивает элементы в способом, подходящим для вашего приложения.  
  
 В языке C++ определены оператора сравнения ( `==`) для простых типов ( `char`, `int`, **float**и так далее), но не определяет оператор сравнения для классов и структур. Если вы хотите использовать `CompareElements` или для создания экземпляра одного из классов коллекций, которые использует его, необходимо определить оператор сравнения или перегрузка `CompareElements` с версией, которая возвращает соответствующие значения.  
  
### <a name="requirements"></a>Требования  
   **Заголовок:** afxtempl.h   
  
##  <a name="copyelements"></a>CopyElements  
 Эта функция вызывается непосредственно [CArray::Append](carray-class.md#append) и [CArray::Copy](carray-class.md#copy).  
  
```   
template<class TYPE>  
void AFXAPI CopyElements(
    TYPE* pDest,  
    const TYPE* pSrc,  
    INT_PTR nCount);  
```  
  
### <a name="parameters"></a>Параметры  
 *ТИП*  
 Параметр шаблона, указав тип элементов для копирования.  
  
 `pDest`  
 Указатель в место назначения, куда будут скопированы элементы.  
  
 `pSrc`  
 Указатель на источник копируемых элементов.  
  
 `nCount`  
 Число копируемых элементов.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию использует простой оператор присваивания ( ** = ** ) для выполнения операции копирования. Если при копировании типа нет перегруженного оператора =, реализация по умолчанию выполняет побитовое копирование.  
  
 Сведения о реализации этого и других вспомогательных функций, см. в статье [коллекций: осуществление строго типизированную коллекцию](../how-to-make-a-type-safe-collection.md).  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxtempl.h  
  
##  <a name="dumpelements"></a>DumpElements  
 Для элементов коллекции при переопределении предоставляет поточно ориентированный диагностические данные в виде текста.  
  
```   
template<class TYPE>  
void  AFXAPI DumpElements(
    CDumpContext& dc,  
    const TYPE* pElements,  
    INT_PTR nCount);  
```  
  
### <a name="parameters"></a>Параметры  
 `dc`  
 Дамп контекста для дампа элементов.  
  
 *ТИП*  
 Параметр шаблона, указав тип элементов.  
  
 `pElements`  
 Указатель на элементы, которые будут выводиться.  
  
 `nCount`  
 Число элементов в дамп.  
  
### <a name="remarks"></a>Примечания  
 **CArray::Dump**, **CList::Dump**, и **CMap::Dump** функции вызывать его, если глубина дампа больше 0.  
  
 Реализация по умолчанию не выполняет никаких действий. Если элементами коллекции являются производными от `CObject`, переопределение обычно перебора элементов коллекции, вызов `Dump` для каждого элемента, в свою очередь.  
  

### <a name="requirements"></a>Требования  
  **Заголовок** afxtempl.h  
  
##  <a name="hashkey"></a>HashKey  
 Вычисляет хэш-значение для заданного ключа.  
  
```  
template<class ARG_KEY>  
AFX_INLINE UINT AFXAPI HashKey(ARG_KEY  key); 
```  
  
### <a name="parameters"></a>Параметры  
 `ARG_KEY`  
 Параметр шаблона, указав тип данных, используемый для доступа к разделам карты.  
  
 `key`  
 Ключ хэша, значение которого необходимо вычислить.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Хэш-значение ключа.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается непосредственно [CMap::RemoveKey](cmap-class.md#removekey) и косвенно [CMap::Lookup](cmap-class.md#lookup) и [[CMap::Operator]](cmap-class.md#operator_at).
  
 Реализация по умолчанию создает значение хэша, переключившись `key` прямо с четырех позиций. Эту функцию можно переопределите, чтобы он возвращал хэш-значения для вашего приложения.  
  
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
 Параметр шаблона, указав тип элементов.  
  
 `ar`  
 Объект для архивации в архив.  
  
 `pElements`  
 Указатель на элементы архивирования.  
  
 `nCount`  
 Количество элементов архивирования  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию не побитовой операции чтения или записи.  
  
 Сведения о реализации этого и других вспомогательных функций, см. в статье [коллекций: осуществление строго типизированную коллекцию](../how-to-make-a-type-safe-collection.md).  
  
### <a name="example"></a>Пример  
 Пример см. в статье [коллекций: осуществление строго типизированную коллекцию](../how-to-make-a-type-safe-collection.md).  
 
### <a name="requirements"></a>Требования  
  **Заголовок** afxtempl.h 
    
## <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](mfc-macros-and-globals.md)   
 [Класс CMap](cmap-class.md)   
 [CList-класс](clist-class.md)   
 [CArray-класс](carray-class.md)
