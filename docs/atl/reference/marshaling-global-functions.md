---
title: Маршалинг глобальные функции | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlbase/ATL::AtlFreeMarshalStream
- atlbase/ATL::AtlMarshalPtrInProc
- atlbase/ATL::AtlUnmarshalPtr
dev_langs:
- C++
ms.assetid: 877100b5-6ad9-44c5-a2e0-09414f1720d0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6d93839002ce5136d735e4740388109e855561fb
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32362831"
---
# <a name="marshaling-global-functions"></a>Маршалинг глобальные функции
Эти функции обеспечивают поддержку маршалинг и преобразование указателя на интерфейс маршалинг данных.  
  
> [!IMPORTANT]
>  Функции, перечисленные в следующей таблице, не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
|||  
|-|-|  
|[AtlFreeMarshalStream](#atlfreemarshalstream)|Освобождает данные маршалинга и `IStream` указателя.|  
|[AtlMarshalPtrInProc](#atlmarshalptrinproc)|Создает новый объект потока и маршалирует заданный указатель интерфейса.|  
|[AtlUnmarshalPtr](#atlunmarshalptr)|Преобразует данные маршалинга потока в указатель на интерфейс.|  

## <a name="requirements"></a>Требования:
**Заголовок:** atlbase.h
  
##  <a name="atlfreemarshalstream"></a>  AtlFreeMarshalStream  
 Освобождает данные маршалинга в потоке, затем освобождает указатель потока.  

```
HRESULT AtlFreeMarshalStream(IStream* pStream);
```  
  
### <a name="parameters"></a>Параметры  
 `pStream`  
 [in] Указатель на `IStream` интерфейса на поток, используемый для маршалинга.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [AtlMarshalPtrInProc](#atlmarshalptrinproc).  
  
##  <a name="atlmarshalptrinproc"></a>  AtlMarshalPtrInProc  
 Создает новый объект потока, записывает в поток CLSID прокси-сервера и маршалирует заданный указатель интерфейса, записывая в поток данные, необходимые для инициализации прокси-сервера.  
  
```
HRESULT AtlMarshalPtrInProc(
    IUnknown* pUnk,
    const IID& iid,
    IStream** ppStream);
```  
  
### <a name="parameters"></a>Параметры  
 *pUnk*  
 [in] Указатель на интерфейс для маршалинга.  
  
 `iid`  
 [in] Идентификатор GUID интерфейса производится маршалинг.  
  
 `ppStream`  
 [out] Указатель на `IStream` интерфейса на новый объект потока, используемые для маршалинга.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 **MSHLFLAGS_TABLESTRONG** флаг установлен, указатель может быть маршалирован в несколько потоков. Указатель также можно распаковать несколько раз.  
  
 Если маршалинг происходит сбой, освобождается указатель потока.  
  
 `AtlMarshalPtrInProc` может использоваться только с указателем на объект в процессе.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_COM#50](../../atl/codesnippet/cpp/marshaling-global-functions_1.cpp)]  
  
##  <a name="atlunmarshalptr"></a>  AtlUnmarshalPtr  
 Преобразует данные маршалинга потока в указатель интерфейса, который может использоваться клиентом.  
   
```
HRESULT AtlUnmarshalPtr(
    IStream* pStream,
    const IID& iid,
    IUnknown** ppUnk);
```  
  
### <a name="parameters"></a>Параметры  
 `pStream`  
 [in] Указатель на поток обрабатывает команды.  
  
 `iid`  
 [in] Идентификатор GUID интерфейса, который обрабатывает команды.  
  
 `ppUnk`  
 [out] Указатель на интерфейс распаковать.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [AtlMarshalPtrInProc](#atlmarshalptrinproc).  
  
## <a name="see-also"></a>См. также  
 [Функции](../../atl/reference/atl-functions.md)
