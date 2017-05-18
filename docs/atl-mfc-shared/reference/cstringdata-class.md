---
title: "Класс CStringData | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CStringData
- ATLSIMPSTR/ATL::CStringData
- ATLSIMPSTR/ATL::AddRef
- ATLSIMPSTR/ATL::data
- ATLSIMPSTR/ATL::IsLocked
- ATLSIMPSTR/ATL::IsShared
- ATLSIMPSTR/ATL::Lock
- ATLSIMPSTR/ATL::Release
- ATLSIMPSTR/ATL::Unlock
- ATLSIMPSTR/ATL::nAllocLength
- ATLSIMPSTR/ATL::nDataLength
- ATLSIMPSTR/ATL::nRefs
- ATLSIMPSTR/ATL::pStringMgr
dev_langs:
- C++
helpviewer_keywords:
- CStringData class
- shared classes, CStringData
ms.assetid: 4e31b5ca-3dbe-4fd5-b692-8211fbfb2593
caps.latest.revision: 16
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: b7dfebebbec7acc774fa2e63ab9fafed788f679a
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="cstringdata-class"></a>Класс CStringData
Этот класс представляет данные строкового объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```
struct CStringData
```  
  
## <a name="members"></a>Члены  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[Метод AddRef](#addref)|Увеличивает значение счетчика ссылок объекта строки данных.|  
|[data](#data)|Возвращает символьные данные строкового объекта.|  
|[Блокирована](#islocked)|Определяет, если буфер соответствующий строковый объект заблокирован.|  
|[IsShared](#isshared)|Определяет, если буфер соответствующий строковый объект является общей.|  
|[Блокировка](#lock)|Блокирует буфер соответствующий строковый объект.|  
|[Релиз](#release)|Освобождает объект указанную строку.|  
|[Разблокировать](#unlock)|Разблокирует буфер соответствующий строковый объект.|  
  
### <a name="data-members"></a>Элементы данных  
  
|||  
|-|-|  
|[nAllocLength](#nalloclength)|Длина выделенных данных в `XCHAR`s (не включая завершающий)|  
|[nDataLength](#ndatalength)|Длина данных в настоящее время используется в `XCHAR`s (не включая завершающий)|  
|[nRefs](#nrefs)|Текущий счетчик ссылок объекта.|  
|[pStringMgr](#pstringmgr)|Указатель на диспетчер строки этого объекта string.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс следует использовать только разработчиками для реализации пользовательской строки диспетчеров. Дополнительные сведения о пользовательской строки диспетчеры см [управление памятью и CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)  
  
 Этот класс инкапсулирует различные виды информации и данных, связанных с высоким строковый объект, например [CStringT](../../atl-mfc-shared/reference/cstringt-class.md), [CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md), или [CFixedStringT](../../atl-mfc-shared/reference/cfixedstringt-class.md) объектов. Каждый выше строковый объект содержит указатель на связанный с ним `CStringData` объекта, позволяя несколько строковых объектов, чтобы она указывала на тот же строковый объект данных. Это отношение представлено счетчик ссылок ( `nRefs`) из `CStringData` объекта.  
  
> [!NOTE]
>  В некоторых случаях тип строки (такие как **CFixedString**) не будет передавать объект строки данных с более чем одного выше объекта string. Дополнительные сведения об этом см. в разделе [управление памятью и CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
 Эти данные состоит из:  
  
-   Диспетчер памяти (типа [IAtlStringMgr](../../atl-mfc-shared/reference/iatlstringmgr-class.md)) строки.  
  
-   Текущая длина ( [nDataLength](#ndatalength)) строки.  
  
-   Длина выделенного ( [nAllocLength](#nalloclength)) строки. Для повышения производительности оно может отличаться от текущей длины строки  
  
-   Текущее количество ссылок ( [nRefs](#nrefs)) из `CStringData` объекта. Это значение используется в определении того, сколько объектов строки совместно используют же `CStringData` объекта.  
  
-   Фактический символ буфера ( [данные](#data)) строки.  
  
    > [!NOTE]
    >  Фактический символ буфера объекта string выделяется диспетчером строки и добавляется к `CStringData` объекта.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlsimpstr.h  
  
##  <a name="addref"></a>CStringData::AddRef  
 Увеличивает значение счетчика ссылок объекта string.  
  
```
void AddRef() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Увеличивает значение счетчика ссылок объекта string.  
  
> [!NOTE]
>  Не вызывать этот метод для строки с отрицательным счетчик, так как отрицательное число указывает, что буфер строки блокируется.  
  
##  <a name="data"></a>CStringData::data  
 Возвращает указатель на буфер символов строкового объекта.  
  
```
void* data() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на буфер символов строкового объекта.  
  
### <a name="remarks"></a>Примечания  
 Эта функция используется для возврата текущего буфера символ объекта связанной строки.  
  
> [!NOTE]
>  Этот буфер не выделен функцией `CStringData` объекта, но диспетчером строки, при необходимости. При выделении, буфер добавляется объект строки данных.  
  
##  <a name="islocked"></a>CStringData::IsLocked  
 Определяет, если буфер символов блокируется.  
  
```
bool IsLocked() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** если буфер заблокирован; в противном случае **false**.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается для определения, если в настоящий момент заблокирован буфер символов строкового объекта.  
  
##  <a name="isshared"></a>CStringData::IsShared  
 Определяет, если буфер символов используется совместно.  
  
```
bool IsShared() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** если буфер общего; в противном случае **false**.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается для определения, если буфер символов строкового объекта данных в настоящее время является общим для нескольких строковых объектов.  
  
##  <a name="lock"></a>CStringData::Lock  
 Блокирует буфер символов связанные строкового объекта.  
  
```
void Lock() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается для блокировки буфер символов строкового объекта данных. Блокировка и снятие блокировки используется, когда требуется прямой доступ к буферу символов разработчиком. Хорошим примером блокировки рассмотренные [LockBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#lockbuffer) и [UnlockBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#unlockbuffer) методы `CSimpleStringT`.  
  
> [!NOTE]
>  Буфер символов могут быть заблокированы, только если буфер не является общим для выше строковых объектов.  
  
##  <a name="nalloclength"></a>CStringData::nAllocLength  
 Длина буфера, выделенного символа.  
  
```
int nAllocLength;
```  
  
### <a name="remarks"></a>Примечания  
 Хранит длина буфера выделенные данные в `XCHAR`s (не включая завершающий нуль).  
  
##  <a name="ndatalength"></a>CStringData::nDataLength  
 Текущая длина объекта string.  
  
```
int nDataLength;
```  
  
### <a name="remarks"></a>Примечания  
 Сохраняет длину данных, используемой в настоящий момент в `XCHAR`s (не включая завершающий нуль).  
  
##  <a name="nrefs"></a>CStringData::nRefs  
 Счетчик ссылок объекта строки данных.  
  
```
long nRefs;
```  
  
### <a name="remarks"></a>Примечания  
 Содержит счетчик ссылок объекта строки данных. Этот счетчик указывает количество выше строковых объектов, связанных с объектом данных строки. Отрицательное значение указывает, что строковый объект данных в настоящее время заблокирован.  
  
##  <a name="pstringmgr"></a>CStringData::pStringMgr  
 Диспетчер памяти связанного строкового объекта.  
  
```
IAtlStringMgr* pStringMgr;
```  
  
### <a name="remarks"></a>Примечания  
 Хранит диспетчер памяти для объекта связанной строки. Дополнительные сведения о диспетчеры памяти и строках см [управление памятью и CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
##  <a name="release"></a>CStringData::Release  
 Уменьшает счетчик ссылок объекта строки данных.  
  
```
void Release() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается для уменьшения числа ссылок, освобождая `CStringData` структуры, если число ссылок достигает нуля. Это часто делается при строковый объект удаляется и поэтому больше не ссылается на объект данных строки.  
  
 Например, следующий код вызовет `CStringData::Release` для строки данных объекта, связанного с `str1`:  
  
 [!code-cpp[NVC_ATLMFC_Utilities&#104;](../../atl-mfc-shared/codesnippet/cpp/cstringdata-class_1.cpp)]  
  
##  <a name="unlock"></a>CStringData::Unlock  
 Разблокирует буфер символов связанные строкового объекта.  
  
```
void Unlock() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается для разблокировки буфер символов строкового объекта данных. После буфера будет разблокирован, он является совместно используемым и могут быть подсчитаны ссылки.  
  
> [!NOTE]
>  Каждый вызов `Lock` должна совпадать с соответствующим вызовом метода `Unlock`.  
  
 Блокировка и снятие блокировки используется, когда разработчик должен убедиться, что строковые данные не будут передаваться. Хорошим примером блокировки рассмотренные [LockBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#lockbuffer) и [UnlockBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#unlockbuffer) методы `CSimpleStringT`.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы общих библиотек ATL и MFC](../../atl-mfc-shared/atl-mfc-shared-classes.md)



