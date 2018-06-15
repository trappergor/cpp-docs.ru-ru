---
title: Развертывание с помощью технологии ClickOnce для приложений Visual C++ | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- deploying applications [C++], ClickOnce
- application deployment [C++], ClickOnce
- ClickOnce deployment [C++], C++ applications
ms.assetid: 9988c546-0936-452c-932f-9c76daa42157
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e85ec0dfc011aab4d2b3ac835bbe71782b055000
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2018
ms.locfileid: "33332329"
---
# <a name="clickonce-deployment-for-visual-c-applications"></a>Развертывание с помощью технологии ClickOnce для приложений Visual C++
Visual Studio предоставляет две различных технологии развертывания приложений Windows: ClickOnce и [установщик Windows](http://msdn.microsoft.com/library/cc185688).  
  
## <a name="clickonce-deployment-in-c"></a>Развертывание с помощью технологии ClickOnce в C++  
 Среда разработки Visual C++ не поддерживает непосредственно развертывание проектов Visual C++ с помощью ClickOnce, но для этого существуют специальные средства.  
  
> [!NOTE]
>  Visual Studio поддерживает ClickOnce в средах развертывания Visual C# и Visual Basic. Если проект Visual C++ зависит от проекта Visual C#, можно опубликовать приложение (включая его зависимости) с помощью развертывания ClickOnce из среды развертывания Visual C#.  
  
 Для развертывания приложения Visual C++ с помощью ClickOnce сначала нужно создать [Манифест приложения ClickOnce](/visualstudio/deployment/clickonce-application-manifest) и [Манифест развертывания ClickOnce](/visualstudio/deployment/clickonce-deployment-manifest) с помощью [Mage.exe](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool) (Инструмент создания и изменения манифестов) или его версий для графического пользовательского интерфейса (сведения см. в разделе [MageUI.exe (средство создания и редактирования манифестов, графический клиент)](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client)).  

  
 Используя Mage.exe, создайте манифест приложения; полученный файл будет иметь расширение MANIFEST. Затем с помощью Mage.exe создайте манифест развертывания; полученный файл будет иметь расширение APPLICATION. Теперь необходимо подписать манифесты.  
  
 В манифесте приложения должен быть указан целевой процессор (**x86**, **x64** или **ARM**). Сведения об этих вариантах см. в разделе [Предварительные условия для развертывания 64-разрядных приложений](/visualstudio/deployment/deploying-prerequisites-for-64-bit-applications).  
  
 Кроме этого, имена манифестов приложения и развертывания не должны совпадать с именем приложения С++. Это позволит избежать конфликта между манифестом приложения, созданным с помощью Mage.exe, и внешним манифестом, являющимся частью приложения C++.  
  
 При развертывании должны быть установлены все библиотеки Visual C++, от которых зависит работа приложения. Чтобы определить зависимости для конкретного приложения, можно воспользоваться файлом depends.exe или служебной программой DUMPBIN, запустив ее с параметром /DEPENDENTS. Дополнительные сведения о зависимостях см. в разделе [Основные сведения о зависимостях приложения Visual C++](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md). Может возникнуть потребность в выполнении VCRedist.exe; эта служебная программа устанавливает библиотеки Visual C++ на конечный компьютер.  
  
 Может также потребоваться создать начальный загрузчик (установщик необходимых компонентов) для приложения, чтобы развернуть необходимые компоненты. Подробнее о начальном загрузчике см. в разделе [Создание пакетов загрузчика](/visualstudio/deployment/creating-bootstrapper-packages).  
  
 Подробные сведения об этой технологии представлены в разделе [Развертывание и безопасность технологии ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment). Подробный пример развертывания ClickOnce см. в разделе [Пошаговое руководство. Развертывание вручную приложения ClickOnce](/visualstudio/deployment/walkthrough-manually-deploying-a-clickonce-application).  
  
## <a name="see-also"></a>См. также  
 [Mage.exe (средство создания и редактирования манифеста)](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool)   
 [MageUI.exe (средство создания и редактирования манифестов, графический клиент)](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client)   
 [Makecert.exe (средство создания сертификатов)](https://msdn.microsoft.com/library/windows/desktop/aa386968)   
 [Развертывание классических приложений](../ide/deploying-native-desktop-applications-visual-cpp.md)   
 [Развертывание приложений, служб и компонентов](/visualstudio/deployment/deploying-applications-services-and-components)   
 [Развертывание с помощью установщика Windows](http://msdn.microsoft.com/en-us/121be21b-b916-43e2-8f10-8b080516d2a0)   
 [Развертывание и безопасность технологии ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment)   
 [Создание пакетов загрузчика](/visualstudio/deployment/creating-bootstrapper-packages)   
 [Программирование .NET с использованием C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)   
 [Взаимодействие исходного кода и платформы.NET](../dotnet/native-and-dotnet-interoperability.md)