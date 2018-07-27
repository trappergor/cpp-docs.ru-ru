---
title: Глобальные функции для маршалинга | Документация Майкрософт
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
ms.openlocfilehash: 44c5205416ff19eeb849b0532d015275e4eb166e
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2018
ms.locfileid: "37879343"
---
# <a name="marshaling-global-functions"></a>Глобальные функции для маршалинга
Эти функции обеспечивают поддержку маршалинг и преобразование указателя на интерфейс маршалинг данных.  
  
> [!IMPORTANT]
>  Функции, перечисленные в следующей таблице, не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
|||  
|-|-|  
|[AtlFreeMarshalStream](#atlfreemarshalstream)|Освобождает данные маршалинга и `IStream` указатель.|  
|[AtlMarshalPtrInProc](#atlmarshalptrinproc)|Создает новый объект потока и маршалирует заданный указатель интерфейса.|  
|[AtlUnmarshalPtr](#atlunmarshalptr)|Преобразует данные маршалинга потока в указатель интерфейса.|  

## <a name="requirements"></a>Требования:
**Заголовок:** atlbase.h
  
##  <a name="atlfreemarshalstream"></a>  AtlFreeMarshalStream  
 Освобождает данные маршалинга в потоке, затем освобождает указатель потока.  

```
HRESULT AtlFreeMarshalStream(IStream* pStream);
```  
  
### <a name="parameters"></a>Параметры  
 *pStream*  
 [in] Указатель на `IStream` интерфейса на поток, используемый для маршалинга.  
  
### <a name="example"></a>Пример  
  См. в примере [AtlMarshalPtrInProc](#atlmarshalptrinproc).  
  
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
  
 *IID*  
 [in] Идентификатор GUID интерфейса маршалируемого.  
  
 *ppStream*  
 [out] Указатель на `IStream` интерфейса на новый объект-поток, используемый для маршалинга.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Этот флаг MSHLFLAGS_TABLESTRONG имеет значение, указатель может быть маршалирован в несколько потоков. Указатель также может быть неупакованный несколько раз.  
  
 Если маршалинг происходит сбой, освобождается указатель потока.  
  
 `AtlMarshalPtrInProc` может использоваться только на указатель на объект в процессе.  
  
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
 *pStream*  
 [in] Указатель на поток обрабатывает команды.  
  
 *IID*  
 [in] Идентификатор GUID интерфейса обрабатывает команды.  
  
 *ppUnk*  
 [out] Указатель на интерфейс неупакованный.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="example"></a>Пример  
  См. в примере [AtlMarshalPtrInProc](#atlmarshalptrinproc).  
  
## <a name="see-also"></a>См. также  
 [Функции](../../atl/reference/atl-functions.md)
