---
title: "Развертывание ClickOnce для приложений Visual C++ | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- deploying applications [C++], ClickOnce
- application deployment [C++], ClickOnce
- ClickOnce deployment [C++], C++ applications
ms.assetid: 9988c546-0936-452c-932f-9c76daa42157
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e1a036a1520a747448c5541f367f0b43711e30b1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="clickonce-deployment-for-visual-c-applications"></a>Развертывание с помощью технологии ClickOnce для приложений Visual C++
Visual Studio предоставляет две различных технологии развертывания приложений Windows: развертывание ClickOnce или [установщика Windows](http://msdn.microsoft.com/library/cc185688) развертывания.  
  
## <a name="clickonce-deployment-in-c"></a>Развертывание с помощью технологии ClickOnce в C++  
 В среде разработки Visual C++ не поддерживает непосредственно развертывание проектов Visual C++ с помощью технологии ClickOnce, но средства доступны для его использования.  
  
> [!NOTE]
>  В средах разработки Visual C# и Visual Basic, Visual Studio поддерживает ClickOnce. Если проект Visual C++: зависимость от проекта Visual C#, можно опубликовать приложение (включая все зависимости) с помощью развертывания ClickOnce из среды разработки Visual C#.  
  
 Развертывание приложения Visual C++ с помощью ClickOnce, сначала нужно построить [манифест приложения ClickOnce](/visualstudio/deployment/clickonce-application-manifest) и [манифест развертывания ClickOnce](/visualstudio/deployment/clickonce-deployment-manifest) с помощью [Mage.exe (манифест Средство создания и изменения)](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool) или его версия графического пользовательского интерфейса (сведения см. в разделе [MageUI.exe (средство создания и манифеста редактирования, графический клиент)](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client)).  

  
 Используя Mage.exe, создайте манифест приложения; полученный файл будет иметь расширение MANIFEST. Затем с помощью Mage.exe создайте манифест развертывания; полученный файл будет иметь расширение APPLICATION. Теперь необходимо подписать манифесты.  
  
 Манифест приложения должен быть указан целевой процессор (**x86**, **x64**, или **ARM**). В разделе [развертывание предварительные требования для 64-разрядных приложений](/visualstudio/deployment/deploying-prerequisites-for-64-bit-applications) сведения об этих параметрах.  
  
 Кроме этого, имена манифестов приложения и развертывания не должны совпадать с именем приложения С++. Это позволит избежать конфликта между манифестом приложения, созданным с помощью Mage.exe, и внешним манифестом, являющимся частью приложения C++.  
  
 Развертывание необходимо установить все библиотеки Visual C++, от которых зависит приложение. Чтобы определить зависимости для конкретного приложения, можно воспользоваться файлом depends.exe или служебной программой DUMPBIN, запустив ее с параметром /DEPENDENTS. Дополнительные сведения о зависимостях см. в разделе [основные сведения о зависимостях приложения Visual C++](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md). Может потребоваться при выполнении VCRedist.exe; Эта служебная программа устанавливает библиотеки Visual C++ на конечном компьютере.  
  
 Может также необходимы для создания загрузчика (установщика необходимых компонентов) приложения для развертывания необходимых компонентов; сведения о загрузчике см. в разделе [создание пакетов загрузчика](/visualstudio/deployment/creating-bootstrapper-packages).  
  
 Более подробное описание технологии см. в разделе [развертывание и безопасность технологии ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment). Подробный пример развертывания ClickOnce см. в разделе [Пошаговое руководство: развертывание вручную приложения ClickOnce](/visualstudio/deployment/walkthrough-manually-deploying-a-clickonce-application).  
  
## <a name="see-also"></a>См. также  
 [Mage.exe (средство создания и редактирования манифеста)](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool)   
 [MageUI.exe (средство создания и редактирования манифестов, графический клиент)](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client)   
 [Makecert.exe (средство создания сертификатов)](https://msdn.microsoft.com/library/windows/desktop/aa386968)   
 [Развертывание приложений для настольных систем](../ide/deploying-native-desktop-applications-visual-cpp.md)   
 [Развертывание приложений, служб и компонентов](/visualstudio/deployment/deploying-applications-services-and-components)   
 [Развертывание с помощью установщика Windows](http://msdn.microsoft.com/en-us/121be21b-b916-43e2-8f10-8b080516d2a0)   
 [Развертывание и безопасность технологии ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment)   
 [Создание пакетов загрузчика](/visualstudio/deployment/creating-bootstrapper-packages)   
 [Программирование .NET с использованием C + +/ CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)   
 [Взаимодействие исходного кода и платформы.NET](../dotnet/native-and-dotnet-interoperability.md)