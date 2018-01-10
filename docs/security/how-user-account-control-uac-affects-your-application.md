---
title: "Влияние контроля учетных записей (UAC) приложение | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- UAC [C++]
- security [C++], User Account Control
- user accounts [C++]
- User Account Control [C++]
ms.assetid: 0d001870-253e-4989-b689-f78035953799
caps.latest.revision: "5"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e609c16d63974506a06d6ec553cf4be09509acb9
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/03/2018
---
# <a name="how-user-account-control-uac-affects-your-application"></a>Влияние контроля учетных записей на приложение
Возможность контроля учетных записей в Windows Vista используется для назначения учетным записям ограниченных привилегий. Подробные сведения о функции контроля учетных записей см. на следующих веб-сайтах:  
  
-   [Пользователь учетной записи управления Пошаговое руководство по Windows Vista](http://go.microsoft.com/fwlink/p/?linkid=53781)  
  
-   [Передовые методики и рекомендации для приложений в среде с минимальными правами](http://go.microsoft.com/fwlink/p/?linkid=82444)  
  
-   [Чтобы настроить контроль учетных записей пользователей в Windows Vista](http://go.microsoft.com/fwlink/p/?linkid=82445)  
  
## <a name="building-projects-after-enabling-uac"></a>Сборка проектов после включения контроля учетных записей  
 Чтобы обеспечить корректную работу проекта Visual C++ для Windows Vista, собранного при отключенном контроле учетных записей, после включения контроля следует выполнить очистку и повторную сборку проекта.  
  
## <a name="applications-that-require-administrative-privileges"></a>Приложения, для которых требуются права администратора  
 Компоновщик Visual C++ по умолчанию внедряет в манифест приложения фрагмент функции контроля учетных записей с уровнем выполнения `asInvoker`. Если для корректного выполнения приложения требуются права администратора (например, если в приложении изменяется узел HKLM реестра или выполняется запись в защищенные разделы диска, такие как каталог Windows), необходимо изменить приложение.  
  
 Первый вариант — Изменить фрагмент контроля учетных Записей манифеста, чтобы изменить уровень выполнения для *requireAdministrator*. В этом случае перед выполнением приложения отображается запрос на ввод учетных данных администратора. Сведения о том, как это сделать в разделе [/MANIFESTUAC (встраивает UAC сведения в манифесте)](../build/reference/manifestuac-embeds-uac-information-in-manifest.md).  
  
 Второй вариант — отменить внедрение фрагмента контроля учетных Записей в манифест, указав **: no** компоновщика. В этом случае приложение выполняется в режиме виртуализации. Любые изменения, вносимые в реестр или файловую систему, не сохраняются после завершения работы приложения.  
  
 На следующей блок-схеме описывается порядок выполнения приложения в зависимости от использования функции и манифеста контроля учетных записей приложения:  
  
 ![Поведение загрузчика Windows Vista](media/uacflowchart.png "UACflowchart")  
  
## <a name="see-also"></a>См. также  
 [Рекомендации по безопасности](security-best-practices-for-cpp.md)