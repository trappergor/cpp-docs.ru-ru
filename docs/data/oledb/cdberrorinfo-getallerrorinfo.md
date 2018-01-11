---
title: "CDBErrorInfo::GetAllErrorInfo | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.CDBErrorInfo.GetAllErrorInfo
- CDBErrorInfo::GetAllErrorInfo
- ATL::CDBErrorInfo::GetAllErrorInfo
- GetAllErrorInfo
- CDBErrorInfo.GetAllErrorInfo
dev_langs: C++
helpviewer_keywords: GetAllErrorInfo method
ms.assetid: 630049fa-d296-497a-bbf6-f5d3d71d271d
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 46e233800f814b39e4e14f0b357c381a3e71311e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cdberrorinfogetallerrorinfo"></a>CDBErrorInfo::GetAllErrorInfo
Возвращает все типы сведений об ошибках, содержащиеся в записи об ошибке.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      HRESULT GetAllErrorInfo(  
   ULONG ulRecordNum,  
   LCID lcid,  
   BSTR* pbstrDescription,  
   BSTR* pbstrSource = NULL,  
   GUID* pguid = NULL,  
   DWORD* pdwHelpContext = NULL,  
   BSTR* pbstrHelpFile = NULL  
) const throw( );  
```  
  
#### <a name="parameters"></a>Параметры  
 *ulRecordNum*  
 [in] Отсчитываемый от нуля номер записи, для которой возвращаются сведения об ошибке.  
  
 `lcid`  
 [in] КОД языка должны быть возвращены сведения об ошибке.  
  
 `pbstrDescription`  
 [out] Указатель на текстовое описание ошибки или значение NULL, если языковой стандарт не поддерживается. См. заметки.  
  
 `pbstrSource`  
 [out] Указатель на строку, содержащую имя компонента, вызвавшего ошибку.  
  
 `pguid`  
 [out] Указатель на идентификатор GUID интерфейса, определившего ошибку.  
  
 *pdwHelpContext*  
 [out] Указатель на идентификатор контекста справки для ошибки.  
  
 *pbstrHelpFile*  
 [out] Указатель на строку, содержащую путь к файлу справки, содержащим описание ошибки.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `S_OK` в случае успешного выполнения. В разделе [IErrorRecords::GetErrorInfo](https://msdn.microsoft.com/en-us/library/ms711230.aspx) в *Справочник программиста OLE DB* для других возвращаемых значений.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="remarks"></a>Примечания  
 Выходное значение `pbstrDescription` внутренним образом получается путем вызова IErrorInfo::GetDescription, который присваивает значение NULL, если языковой стандарт не поддерживается, или в том случае, если выполняются оба из следующих условий:  
  
1.  значение `lcid` не США Английский и  
  
2.  значение `lcid` является значение, возвращенное GetUserDefaultLCID не равны.  
  
## <a name="see-also"></a>См. также  
 [Класс CDBErrorInfo](../../data/oledb/cdberrorinfo-class.md)