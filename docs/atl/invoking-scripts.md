---
title: "Вызов скрипты (ATL) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: StringRegister
dev_langs: C++
helpviewer_keywords:
- StringRegister method
- scripts, invoking registry in ATL
ms.assetid: eabd41ee-586b-4266-9e92-5aaad04b73a4
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7cbf969f601bd90e84bf0ee15ae2ea3dcb392610
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="invoking-scripts"></a>Вызов скриптов
[Использование подстановочных параметров (препроцессор регистратора)](../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md) рассматриваются замены карты и указывается метод регистратора **AddReplacement**. Регистратор имеет восемь других методов, определенных в построении сценариев, и все описаны в следующей таблице.  
  
|Метод|Описание синтаксиса|  
|------------|-------------------------|  
|**ResourceRegister**|**Значение HRESULT ResourceRegister (LPCOLESTR***resFileName* **, UINT** `nID` **, LPCOLESTR** `szType` **);** <br /><br /> Регистрирует скрипт, содержащийся в модуле ресурсов. *resFileName* указывает путь UNC к сам модуль. `nID`и `szType` содержат ИД ресурса и типом, соответственно.|  
|**ResourceUnregister**|**Значение HRESULT ResourceUnregister (LPCOLESTR***resFileName* **, UINT** `nID` **, LPCOLESTR** `szType` **);** <br /><br /> Отменяет регистрацию скрипт, содержащийся в модуле ресурсов. *resFileName* указывает путь UNC к сам модуль. `nID`и `szType` содержат ИД ресурса и типом, соответственно.|  
|**ResourceRegisterSz**|**Значение HRESULT ResourceRegisterSz (LPCOLESTR***resFileName* **, LPCOLESTR***szID* **, LPCOLESTR** `szType` **);** <br /><br /> Регистрирует скрипт, содержащийся в модуле ресурсов. *resFileName* указывает путь UNC к сам модуль. *szID* и `szType` содержат строковый идентификатор ресурса и типом, соответственно.|  
|**ResourceUnregisterSz**|**Значение HRESULT ResourceUnregisterSz (LPCOLESTR***resFileName* **, LPCOLESTR***szID* **, LPCOLESTR** `szType` **);** <br /><br /> Отменяет регистрацию скрипт, содержащийся в модуле ресурсов. *resFileName* указывает путь UNC к сам модуль. *szID* и `szType` содержат строковый идентификатор ресурса и типом, соответственно.|  
|**FileRegister**|**Значение HRESULT FileRegister (LPCOLESTR***fileName***);** <br /><br /> Регистрирует скрипт в файле. *Имя файла* является UNC-путь в файл, содержащий (или) сценария ресурса.|  
|**FileUnregister**|**Значение HRESULT FileUnregister (LPCOLESTR***fileName***);** <br /><br /> Отменяет регистрацию скрипт в файл. *Имя файла* является UNC-путь в файл, содержащий (или) сценария ресурса.|  
|**StringRegister**|**Значение HRESULT StringRegister (LPCOLESTR***данные***);** <br /><br /> Регистрирует скрипт в строке. *данные* содержит сам скрипт.|  
|**StringUnregister**|**Значение HRESULT StringUnregister (LPCOLESTR***данные***);** <br /><br /> Отменяет регистрацию скрипта в строке. *данные* содержит сам скрипт.|  
  
 **ResourceRegisterSz** и **ResourceUnregisterSz**, похожи на **ResourceRegister** и **ResourceUnregister**, но позволяют указать Идентификатор строки.  
  
 Методы **FileRegister** и **FileUnregister** полезны, если не требуется, чтобы скрипт в виде ресурса, или если требуется скрипт в отдельном файле. Методы **StringRegister** и **StringUnregister** разрешить RGS-файл должен храниться в динамически выделенные строки.  
  
## <a name="see-also"></a>См. также  
 [Создание скриптов регистратора](../atl/creating-registrar-scripts.md)

