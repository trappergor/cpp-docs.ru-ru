---
title: "Маршалинг глобальные функции | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: 877100b5-6ad9-44c5-a2e0-09414f1720d0
caps.latest.revision: 19
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
ms.sourcegitcommit: 5187996fc377bca8633360082d07f7ec8a68ee57
ms.openlocfilehash: dd4b8d50ec69974b7b2af29438b1657e1ce592b4
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="marshaling-global-functions"></a>Маршалинг глобальные функции
Эти функции обеспечивают поддержку маршалинг и преобразование указателей интерфейса маршалинг данных.  
  
> [!IMPORTANT]
>  Функции, перечисленные в следующей таблице, не может использоваться в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
|||  
|-|-|  
|[AtlFreeMarshalStream](#atlfreemarshalstream)|Освобождает данные маршалинга и `IStream` указателя.|  
|[AtlMarshalPtrInProc](#atlmarshalptrinproc)|Создает новый объект потока и маршалирует заданный указатель интерфейса.|  
|[AtlUnmarshalPtr](#atlunmarshalptr)|Преобразует данные маршалинга потока в указатель на интерфейс.|  
  
##  <a name="atlfreemarshalstream"></a>AtlFreeMarshalStream  
 Освобождает данные маршалинга в потоке, затем освобождает указатель потока.  

```
HRESULT AtlFreeMarshalStream(IStream* pStream);
```  
  
### <a name="parameters"></a>Параметры  
 `pStream`  
 [in] Указатель на `IStream` интерфейса на поток, используемый для маршалинга.  
  
### <a name="example"></a>Пример  
  В примере показано [AtlMarshalPtrInProc](#atlmarshalptrinproc).  
  
##  <a name="atlmarshalptrinproc"></a>AtlMarshalPtrInProc  
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
 [in] Идентификатор GUID интерфейса маршалируемого.  
  
 `ppStream`  
 [out] Указатель на `IStream` интерфейса на новый объект потока, используемые для маршалинга.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 **MSHLFLAGS_TABLESTRONG** флаг установлен, указатель может быть маршалирован несколько потоков. Указатель также может быть распакованным несколько раз.  
  
 Если маршалинг происходит сбой, освобождается указатель потока.  
  
 `AtlMarshalPtrInProc`может использоваться только с указателем на объект в процессе.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_COM&#50;](../../atl/codesnippet/cpp/marshaling-global-functions_1.cpp)]  
  
##  <a name="atlunmarshalptr"></a>AtlUnmarshalPtr  
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
 [in] Идентификатор GUID интерфейса обрабатывает команды.  
  
 `ppUnk`  
 [out] Указатель на интерфейс распаковать.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="example"></a>Пример  
  В примере показано [AtlMarshalPtrInProc](#atlmarshalptrinproc).  
  
## <a name="see-also"></a>См. также  
 [Функции](../../atl/reference/atl-functions.md)

