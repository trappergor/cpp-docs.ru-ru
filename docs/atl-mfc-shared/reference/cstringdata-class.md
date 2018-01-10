---
title: "Класс CStringData | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
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
dev_langs: C++
helpviewer_keywords:
- CStringData class
- shared classes, CStringData
ms.assetid: 4e31b5ca-3dbe-4fd5-b692-8211fbfb2593
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7523ca52c0ded8ec9b3cf02dd6798beca8be5cf8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cstringdata-class"></a>Класс CStringData
Этот класс представляет данные строкового объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```
struct CStringData
```  
  
## <a name="members"></a>Участники  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[AddRef](#addref)|Увеличивает значение счетчика ссылок объекта строки данных.|  
|[data](#data)|Возвращает символьные данные строкового объекта.|  
|[Блокирована](#islocked)|Определяет, если блокировки буфера объекта связанной строки.|  
|[IsShared](#isshared)|Определяет, если буфер объекта связанные строки является общей.|  
|[Блокировка](#lock)|Блокирует буфер объекта связанные строки.|  
|[Релиз](#release)|Освобождает указанный строчный объект.|  
|[Снятие блокировки](#unlock)|Разблокирует буфер объекта связанные строки.|  
  
### <a name="data-members"></a>Элементы данных  
  
|||  
|-|-|  
|[nAllocLength](#nalloclength)|Длина в выделенных данных `XCHAR`s (не включая завершающий нуль-символ)|  
|[nDataLength](#ndatalength)|Длина данных, используемой в настоящий момент в `XCHAR`s (не включая завершающий нуль-символ)|  
|[nRefs](#nrefs)|Текущий счетчик ссылок объекта.|  
|[pStringMgr](#pstringmgr)|Указатель на диспетчер строку этого объекта string.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс должен использоваться только разработчиками для реализации пользовательской строки диспетчеры. Дополнительные сведения о диспетчеры пользовательской строки в разделе [управление памятью и CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)  
  
 Этот класс инкапсулирует различные виды информации и данных, связанные с более поздней версии, строковые объекты, такие как [CStringT](../../atl-mfc-shared/reference/cstringt-class.md), [CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md), или [CFixedStringT](../../atl-mfc-shared/reference/cfixedstringt-class.md) объекты. Каждый выше строковый объект содержит указатель на связанный с ним `CStringData` объекта, позволяя несколько строковых объектов, чтобы она указывала на тот же строковый объект данных. Эта связь представляется счетчик ссылок ( `nRefs`) из `CStringData` объекта.  
  
> [!NOTE]
>  В некоторых случаях тип строки (такие как **CFixedString**) не будут совместно использовать строковый объект данных с более чем одного выше объекта string. Дополнительные сведения см. в разделе [управление памятью и CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
 Эти данные состоит из:  
  
-   Диспетчер памяти (типа [IAtlStringMgr](../../atl-mfc-shared/reference/iatlstringmgr-class.md)) строки.  
  
-   Текущая длина ( [nDataLength](#ndatalength)) строки.  
  
-   Выделенный длины ( [nAllocLength](#nalloclength)) строки. Для повышения производительности он может отличаться от текущей длины строки  
  
-   Текущее количество ссылок ( [nRefs](#nrefs)) из `CStringData` объекта. Это значение используется в определении, сколько объектов string с одинаковым `CStringData` объекта.  
  
-   Фактический символ буфера ( [данные](#data)) строки.  
  
    > [!NOTE]
    >  Фактический символ буфера объекта string выделяемый диспетчера строки и добавляется к `CStringData` объекта.  
  
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
>  Не вызывайте этот метод для строки с отрицательным счетчик, так как отрицательное число указывает, что строковый буфер блокируется.  
  
##  <a name="data"></a>CStringData::data  
 Возвращает указатель на буфер символов строкового объекта.  
  
```
void* data() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на буфер символов объекта string.  
  
### <a name="remarks"></a>Примечания  
 Эта функция используется для возврата текущего буфера символ объекта связанные строки.  
  
> [!NOTE]
>  Этот буфер не распределен какими `CStringData` объекта, но диспетчером строки, при необходимости. При выделении, буфер добавляется к объекту данных строки.  
  
##  <a name="islocked"></a>CStringData::IsLocked  
 Определяет, если буфер символов заблокирован.  
  
```
bool IsLocked() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** если буфер является заблокированным; в противном случае **false**.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается для определения, если буфер символов строкового объекта в данный момент заблокирована.  
  
##  <a name="isshared"></a>CStringData::IsShared  
 Определяет, если буфер символов используется совместно.  
  
```
bool IsShared() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** если буфер является общей; в противном случае **false**.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается для определения, если буфер символов строкового объекта данных в настоящее время общими для нескольких строковых объектов.  
  
##  <a name="lock"></a>CStringData::Lock  
 Блокирует буфер символов объекта связанные строки.  
  
```
void Lock() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается для блокирования буфера символ объекта строки данных. Блокировка и разблокировка используется, если требуется прямой доступ к буферу символов разработчиком. Хорошим примером блокировки рассмотренные [LockBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#lockbuffer) и [UnlockBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#unlockbuffer) методы `CSimpleStringT`.  
  
> [!NOTE]
>  Буфер символов можно блокировки только в том случае, если буфер не обобщаются между выше строковых объектов.  
  
##  <a name="nalloclength"></a>CStringData::nAllocLength  
 Длина буфера выделенного символа.  
  
```
int nAllocLength;
```  
  
### <a name="remarks"></a>Примечания  
 Сохраняет длина буфера выделенные данные в `XCHAR`s (не включая завершающий нуль-символ).  
  
##  <a name="ndatalength"></a>CStringData::nDataLength  
 Текущая длина объекта string.  
  
```
int nDataLength;
```  
  
### <a name="remarks"></a>Примечания  
 Сохраняет длину данных, используемой в настоящий момент в `XCHAR`s (не включая завершающий нуль-символ).  
  
##  <a name="nrefs"></a>CStringData::nRefs  
 Счетчик ссылок объекта строки данных.  
  
```
long nRefs;
```  
  
### <a name="remarks"></a>Примечания  
 Хранит количество ссылок на объект строки данных. Это число обозначает количество выше строковых объектов, связанных с объектом данных строки. Отрицательное значение указывает на объект строки данных в данный момент заблокирована.  
  
##  <a name="pstringmgr"></a>CStringData::pStringMgr  
 Диспетчер памяти объекта связанные строки.  
  
```
IAtlStringMgr* pStringMgr;
```  
  
### <a name="remarks"></a>Примечания  
 Хранит диспетчера памяти для объекта связанной строки. Дополнительные сведения о диспетчеры памяти и строки в разделе [управление памятью и CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
##  <a name="release"></a>CStringData::Release  
 Уменьшает счетчик ссылок объекта строки данных.  
  
```
void Release() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается для уменьшения числа ссылок, освобождение `CStringData` структуры, если число ссылок достигает нуля. Обычно это делается при строковый объект удаляется и поэтому больше не нужна для ссылки на объект строки данных.  
  
 Например, следующий код вызовет `CStringData::Release` для объекта строки данных, связанные с `str1`:  
  
 [!code-cpp[NVC_ATLMFC_Utilities#104](../../atl-mfc-shared/codesnippet/cpp/cstringdata-class_1.cpp)]  
  
##  <a name="unlock"></a>CStringData::Unlock  
 Разблокирует буфер символов объекта связанные строки.  
  
```
void Unlock() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается для разблокировки буфера символ объекта строки данных. Когда буфер не заблокирован, он становится совместного использования и могут быть подсчитаны ссылки.  
  
> [!NOTE]
>  Каждый вызов `Lock` должна совпадать с соответствующим вызовом `Unlock`.  
  
 Блокировка и разблокировка используется, если разработчик должен убедиться, не совместно строковые данные. Хорошим примером блокировки рассмотренные [LockBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#lockbuffer) и [UnlockBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#unlockbuffer) методы `CSimpleStringT`.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [ATL и MFC общие классы](../../atl-mfc-shared/atl-mfc-shared-classes.md)


