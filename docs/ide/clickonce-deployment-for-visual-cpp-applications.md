---
title: "Развертывание с помощью технологии ClickOnce для приложений Visual C++ | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "развертывание приложений [C++], ClickOnce"
  - "развертывание приложения [C++], ClickOnce"
  - "Развертывание ClickOnce, приложения C++"
ms.assetid: 9988c546-0936-452c-932f-9c76daa42157
caps.latest.revision: 17
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Развертывание с помощью технологии ClickOnce для приложений Visual C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] предоставляет две различных технологии развертывания приложений Windows: ClickOnce и [Установщик Windows](http://msdn.microsoft.com/library/cc185688).  
  
## Развертывание с помощью технологии ClickOnce в C\+\+  
 Среда разработки [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] не поддерживает непосредственно развертывание проектов [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] с помощью [!INCLUDE[ndptecclick](../ide/includes/ndptecclick_md.md)], но для этого существуют специальные средства.  
  
> [!NOTE]
>  [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] поддерживает [!INCLUDE[ndptecclick](../ide/includes/ndptecclick_md.md)] в средах развертывания [!INCLUDE[csprcs](../ide/includes/csprcs_md.md)] и [!INCLUDE[vbprvb](../dotnet/includes/vbprvb_md.md)].  Если проект [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] зависим от проекта [!INCLUDE[csprcs](../ide/includes/csprcs_md.md)], можно опубликовать приложение \(включая все зависимости\) с помощью средств развертывания [!INCLUDE[ndptecclick](../ide/includes/ndptecclick_md.md)] из среды развертывания [!INCLUDE[csprcs](../ide/includes/csprcs_md.md)].  
  
 Для развертывания приложения [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] с помощью [!INCLUDE[ndptecclick](../ide/includes/ndptecclick_md.md)] необходимо в начале создать [Манифест приложения ClickOnce](../Topic/ClickOnce%20Application%20Manifest.md) и [Манифест развертывания ClickOnce](../Topic/ClickOnce%20Deployment%20Manifest.md) с помощью [Mage.exe \(средство создания и редактирования манифеста\)](../Topic/Mage.exe%20\(Manifest%20Generation%20and%20Editing%20Tool\).md) или его версий для графического пользовательского интерфейса \(сведения см. в разделе [MageUI.exe \(Manifest Generation and Editing Tool, Graphical Client\)](../Topic/MageUI.exe%20\(Manifest%20Generation%20and%20Editing%20Tool,%20Graphical%20Client\).md)\).  
  
 Используя Mage.exe, создайте манифест приложения; полученный файл будет иметь расширение MANIFEST.  Затем с помощью Mage.exe создайте манифест развертывания; полученный файл будет иметь расширение APPLICATION.  Теперь необходимо подписать манифесты.  
  
 В манифесте приложения должен быть указан целевой процессор \(**x86**, **x64** или **ARM**\).  Дополнительные сведения об этих параметрах см. в разделе [Предварительные условия для развертывания 64\-разрядных приложений](../Topic/Deploying%20Prerequisites%20for%2064-bit%20Applications.md).  
  
 Кроме этого, имена манифестов приложения и развертывания не должны совпадать с именем приложения С\+\+.  Это позволит избежать конфликта между манифестом приложения, созданным с помощью Mage.exe, и внешним манифестом, являющимся частью приложения C\+\+.  
  
 При развертывании должны быть установлены все библиотеки [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)], от которых зависит работа приложения.  Чтобы определить зависимости для конкретного приложения, можно воспользоваться файлом depends.exe или служебной программой DUMPBIN, запустив ее с параметром \/DEPENDENTS.  Дополнительные сведения о зависимостях см. в разделе [Основные сведения о зависимостях приложения Visual C\+\+](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md).  Может возникнуть потребность в выполнении VCRedist.exe; эта служебная программа устанавливает библиотеки [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] на конечный компьютер.  
  
 Может также возникнуть необходимость создания загрузчика \(установщика необходимых компонентов\) приложения для предварительного развертывания необходимых компонентов; подробнее о загрузчике см. в разделе [Создание пакетов загрузчика](../Topic/Creating%20Bootstrapper%20Packages.md).  
  
 Подробные сведения об этой технологии представлены в разделе [Развертывание и безопасность технологии ClickOnce](../Topic/ClickOnce%20Security%20and%20Deployment.md).  Подробные примеры развертывания [!INCLUDE[ndptecclick](../ide/includes/ndptecclick_md.md)] см. в разделе [Разбор примера: развертывание вручную приложения ClickOnce](../Topic/Walkthrough:%20Manually%20Deploying%20a%20ClickOnce%20Application.md).  
  
## См. также  
 [Mage.exe \(средство создания и редактирования манифеста\)](../Topic/Mage.exe%20\(Manifest%20Generation%20and%20Editing%20Tool\).md)   
 [MageUI.exe \(Manifest Generation and Editing Tool, Graphical Client\)](../Topic/MageUI.exe%20\(Manifest%20Generation%20and%20Editing%20Tool,%20Graphical%20Client\).md)   
 [Makecert.exe \(Certificate Creation Tool\)](../Topic/Makecert.exe%20\(Certificate%20Creation%20Tool\).md)   
 [Развертывание классических приложений](../Topic/Deploying%20Native%20Desktop%20Applications%20\(Visual%20C++\).md)   
 [Развертывание приложений, служб и компонентов](../Topic/Deploying%20Applications,%20Services,%20and%20Components.md)   
 [Windows Installer Deployment](http://msdn.microsoft.com/ru-ru/121be21b-b916-43e2-8f10-8b080516d2a0)   
 [Развертывание и безопасность технологии ClickOnce](../Topic/ClickOnce%20Security%20and%20Deployment.md)   
 [Создание пакетов загрузчика](../Topic/Creating%20Bootstrapper%20Packages.md)   
 [программирование .NET с использованием C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)   
 [Взаимодействие исходного кода и платформы.NET](../Topic/Native%20and%20.NET%20Interoperability.md)