---
title: "Функция CAtlServiceModuleT::Start | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CServiceModule.Start
- CServiceModule::Start
dev_langs: C++
helpviewer_keywords: Start method
ms.assetid: b5193a23-41bc-42d2-8d55-3eb43dc62238
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c3eb7009e8092184effad5e1874297c8c04b213e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="catlservicemoduletstart-function"></a>Функция CAtlServiceModuleT::Start
При запуске служба **_tWinMain** вызовы **CAtlServiceModuleT::WinMain**, который в свою очередь вызывает `CAtlServiceModuleT::Start`.  
  
 `CAtlServiceModuleT::Start`Задает массив **SERVICE_TABLE_ENTRY** структуры, соответствующие каждой службы функцию запуска. Затем этот массив передается функции Win32 API, [StartServiceCtrlDispatcher](http://msdn.microsoft.com/library/windows/desktop/ms686324). В теории одного исполняемого файла может обрабатывать несколько служб, и массив может иметь несколько **SERVICE_TABLE_ENTRY** структуры. Тем не менее, в настоящее время службы создается ATL поддерживает только одна служба в EXE-файла. Таким образом, массив содержит одну запись, которая содержит имя службы и **_ServiceMain** как функцию запуска. **_ServiceMain** является статической функцией-членом из `CAtlServiceModuleT` , которая вызывает функцию-член, `ServiceMain`.  
  
> [!NOTE]
>  Сбой **StartServiceCtrlDispatcher** для подключения к службе управления manager (SCM), скорее всего, означает, что программа не запущена как служба. В этом случае программа вызывает `CAtlServiceModuleT::Run` напрямую, чтобы программу можно запустить как локальный сервер. Дополнительные сведения о запуске программы в качестве локального сервера см. в разделе [советы по отладке](../atl/debugging-tips.md).  
  
## <a name="see-also"></a>См. также  
 [Службы](../atl/atl-services.md)   
 [CAtlServiceModuleT::Start](../atl/reference/catlservicemodulet-class.md#start)

