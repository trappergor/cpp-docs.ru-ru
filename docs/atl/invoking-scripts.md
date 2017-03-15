---
title: "Invoking Scripts | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "StringRegister"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "скрипты, invoking registry in ATL"
  - "StringRegister method"
ms.assetid: eabd41ee-586b-4266-9e92-5aaad04b73a4
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Invoking Scripts
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[Использование подстановочных параметров \(препроцессор регистратора\)](../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md) описывает сопоставления замены и упоминает метод **AddReplacement** регистратора.  Регистратор принимает 8 других методов, определенных в сценарии и описаны в следующей таблице.  
  
|Метод|Синтаксис и описание|  
|-----------|--------------------------|  
|**ResourceRegister**|**HRESULT ResourceRegister\( LPCOLESTR**  *resFileName* **, UINT**  `nID` **, LPCOLESTR**  `szType` **\);**<br /><br /> Регистрирует скрипт, содержащихся в ресурсе модуля.  Указывает путь в формате unc *resFileName* самого к модулю.  `nID` и `szType` содержат идентификатор и тип ресурса, соответственно.|  
|**ResourceUnregister**|**HRESULT ResourceUnregister\( LPCOLESTR**  *resFileName* **, UINT**  `nID` **, LPCOLESTR**  `szType` **\);**<br /><br /> Отменяет регистрацию скрипт, содержащихся в ресурсе модуля.  Указывает путь в формате unc *resFileName* самого к модулю.  `nID` и `szType` содержат идентификатор и тип ресурса, соответственно.|  
|**ResourceRegisterSz**|**HRESULT ResourceRegisterSz\( LPCOLESTR**  *resFileName* **, LPCOLESTR**  *szID* **, LPCOLESTR**  `szType` **\);**<br /><br /> Регистрирует скрипт, содержащихся в ресурсе модуля.  Указывает путь в формате unc *resFileName* самого к модулю.  *szID* и `szType` содержат идентификатор и тип строки ресурсов соответственно.|  
|**ResourceUnregisterSz**|**HRESULT ResourceUnregisterSz\( LPCOLESTR**  *resFileName* **, LPCOLESTR**  *szID* **, LPCOLESTR**  `szType` **\);**<br /><br /> Отменяет регистрацию скрипт, содержащихся в ресурсе модуля.  Указывает путь в формате unc *resFileName* самого к модулю.  *szID* и `szType` содержат идентификатор и тип строки ресурсов соответственно.|  
|**FileRegister**|**HRESULT FileRegister\( LPCOLESTR**  *fileName*  **\);**<br /><br /> Регистрирует скрипт в файле.  *имя файла*  путь в формате unc к файлу, содержащему \(или\) скрипт ресурса.|  
|**FileUnregister**|**HRESULT FileUnregister\( LPCOLESTR**  *fileName*  **\);**<br /><br /> Отменяет регистрацию скрипт в файле.  *имя файла*  путь в формате unc к файлу, содержащему \(или\) скрипт ресурса.|  
|**StringRegister**|**HRESULT StringRegister\( LPCOLESTR**  *data*  **\);**<br /><br /> Регистрирует скрипт в строке.  *данные*  содержат скриптов.|  
|**StringUnregister**|**HRESULT StringUnregister\( LPCOLESTR**  *data*  **\);**<br /><br /> Отменяет регистрацию скрипт в строке.  *данные*  содержат скриптов.|  
  
 **ResourceRegisterSz** и **ResourceUnregisterSz**, похожи на **ResourceRegister** и **ResourceUnregister**, но позволяют указать идентификатор строки.  
  
 Методы **FileRegister** и **FileUnregister** полезны, если не нужно, чтобы в ресурсе скрипт или скрипт в отдельном файле.  Методы **StringRegister** и **StringUnregister** позволяют файл .rgs, сохраняемый в динамически выбранной строки.  
  
## См. также  
 [Creating Registrar Scripts](../Topic/Creating%20Registrar%20Scripts.md)