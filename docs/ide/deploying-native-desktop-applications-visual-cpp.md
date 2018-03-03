---
title: "Развертывание классических приложений неуправляемого кода (Visual C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- deploying applications [C++]
- application deployment [C++]
- Visual C++, application deployment
- application deployment [C++], about application deployment
- deploying applications [C++], about deploying applications
- distributing applications [C++]
ms.assetid: 37f1691e-d67c-41e4-926e-528a237a9bac
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1fe88a322314ac24fa5799735e84ff100efa2e79
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="deploying-native-desktop-applications-visual-c"></a>Развертывание классических приложений неуправляемого кода (Visual C++)
Развертывание — это процесс, с помощью которого готовое приложение или компонент распространяются для установки на других компьютерах. Планирование развертывания начинается при создании приложения на компьютере разработчика. Развертывание завершается, когда приложение установлено и готово для запуска на компьютере пользователя.  
  
 Visual Studio предоставляет различные технологии развертывания приложений Windows. К ним относятся развертывания ClickOnce и развертывания установщика Windows.  
  
-   Можно использовать ClickOnce для развертывания приложений C++, предназначенных для общеязыковой среды выполнения (CLR) — смешанных, чистых и проверяемых сборок. Несмотря на то, что установщик Windows можно использовать для развертывания приложений управляемого кода, рекомендуется использовать ClickOnce, так как она позволяет воспользоваться функциями безопасности .NET Framework, например подписывание манифеста. ClickOnce не поддерживает развертывание приложений с машинным кодом C++. Дополнительные сведения см. в разделе [ClickOnce Deployment for Visual C++ Applications](../ide/clickonce-deployment-for-visual-cpp-applications.md).  
  
-   Установщик Windows можно использовать для развертывания приложений C++ неуправляемого кода или приложений C++, предназначенных для среды CLR.  
  
 В статьях в этом разделе документации рассматриваются следующие вопросы: как проверить работу приложения Visual C++ неуправляемого кода на любом компьютере, предоставляющем поддерживаемую целевую платформу, файлы, которые необходимо включить в пакет установки, и рекомендуемые способы распространения компонентов, от которых зависит работа приложения.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Развертывание в Visual C++](../ide/deployment-in-visual-cpp.md)  
  
 [Концепции развертывания](../ide/deployment-concepts.md)  
  
 [Основные сведения о зависимостях приложения Visual C++](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md)  
  
 [Определение библиотек DLL для распространения](../ide/determining-which-dlls-to-redistribute.md)  
  
 [Выбор метода развертывания](../ide/choosing-a-deployment-method.md)  
  
 [Распространение файлов Visual C++](../ide/redistributing-visual-cpp-files.md)  
  
 [Примеры развертывания](../ide/deployment-examples.md)  
  
 [Распространение клиентских веб-приложений](../ide/redistributing-web-client-applications.md)  
  
 [Развертывание с помощью технологии ClickOnce для приложений Visual C++](../ide/clickonce-deployment-for-visual-cpp-applications.md)  
  
 [Выполнение приложения C++/CLR в предыдущей версии среды выполнения](../ide/running-a-cpp-clr-application-on-a-previous-runtime-version.md)  
  
## <a name="related-sections"></a>Связанные разделы  
 [Создание изолированных приложений и параллельных сборок C/C++](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)  
  
 [Развертывание](/dotnet/framework/deployment/index)  
  
 [Устранение неполадок в изолированных приложениях и параллельных сборках на C/C++](../build/troubleshooting-c-cpp-isolated-applications-and-side-by-side-assemblies.md)