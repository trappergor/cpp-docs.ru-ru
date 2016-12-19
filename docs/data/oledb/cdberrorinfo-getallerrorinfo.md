---
title: "CDBErrorInfo::GetAllErrorInfo | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL.CDBErrorInfo.GetAllErrorInfo"
  - "CDBErrorInfo::GetAllErrorInfo"
  - "ATL::CDBErrorInfo::GetAllErrorInfo"
  - "GetAllErrorInfo"
  - "CDBErrorInfo.GetAllErrorInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetAllErrorInfo - метод"
ms.assetid: 630049fa-d296-497a-bbf6-f5d3d71d271d
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDBErrorInfo::GetAllErrorInfo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Возвращает все типы сведений об ошибке, содержащиеся в записи ошибок.  
  
## Синтаксис  
  
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
  
#### Параметры  
 *ulRecordNum*  
 \[in\] отсчитываются от нуля число записей, для которой для получения сведений об ошибке.  
  
 `lcid`  
 \[in\] код языка для сведений об ошибке, который необходимо вернуть.  
  
 `pbstrDescription`  
 \[out\] указатель на текстовое описание ошибки или NULL, если языковой стандарт не поддерживается.  См. заметки.  
  
 `pbstrSource`  
 \[out\] указатель на строку, содержащую имя компонента, который формирует ошибку.  
  
 `pguid`  
 \[out\] указатель на GUID интерфейса, определившего ошибку.  
  
 *pdwHelpContext*  
 \[out\] указатель на контекстное идентификатор справки для ошибки.  
  
 *pbstrHelpFile*  
 \[out\] указатель на строку, содержащую путь к файлу справки, описывающее ошибку.  
  
## Возвращаемое значение  
 `S_OK`, если операция завершилась успешно.  В разделе [IErrorRecords::GetErrorInfo](https://msdn.microsoft.com/en-us/library/ms711230.aspx) справочника *программиста OLE DB* для других возвращаемых значений.  
  
## Требования  
 **Заголовок:** atldbcli.h  
  
## Заметки  
 Выходное значение `pbstrDescription` осуществляется внутренне путем вызова IErrorInfo::GetDescription, которое задает значение NULL, если языковой стандарт не поддерживается, или при выполнении обоих из следующих условий.  
  
1.  значение `lcid` нет\) и английских  
  
2.  значение `lcid` не равно значению, возвращаемому GetUserDefaultLCID.  
  
## См. также  
 [Класс CDBErrorInfo](../../data/oledb/cdberrorinfo-class.md)