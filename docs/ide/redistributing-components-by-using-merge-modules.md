---
title: "Распространение компонентов с использованием модулей слияния | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "модули слияния, использование"
  - "повторное распространение приложений, использование модулей слияния"
ms.assetid: 93b84211-bf9b-4a78-9f22-474ac2ef7840
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# Распространение компонентов с использованием модулей слияния
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] включает в себя [модули слияния](http://msdn.microsoft.com/library/aa367434) для каждого компонента [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)], лицензированного для распространения вместе с приложением.  Если модуль слияния компилируется в файле установщика Windows, он включает развертывание определенных DLL на компьютерах, имеющих определенную платформу.  В файле установки укажите, что модули слияния являются необходимыми компонентами для вашего приложения.  Если [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] установлена, модули слияния помещаются в папку \\Program Files\\Common Files\\Merge Modules\\. \(Распространять можно только неотладочные версии библиотек DLL [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)].\) Дополнительные сведения и ссылку на список модулей слияния, которые подлежат лицензированию для распространения см. в разделе [Распространение файлов Visual C\+\+](../Topic/Redistributing%20Visual%20C++%20Files.md).  
  
 Модули слияния можно использовать для включения возможности установки распространяемых библиотек DLL [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] в папку %SYSTEMROOT%\\system32\\. \(Сама [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] использует этот метод.\) Однако установка в эту папку завершится неудачей, если у выполняющего установку пользователя нет прав администратора.  
  
 Рекомендуется не использовать модули слияния за исключением тех случаев, когда нет необходимости обслуживания приложения и нет зависимостей от более чем одной версии библиотек DLL.  Модули слияния для разных версий одной и той же библиотеки DLL нельзя включить в один установщик, и модули слияния осложняют поддержку DLL независимо от приложения.  Вместо этого рекомендуется установить распространяемый пакет [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)].  
  
## См. также  
 [Распространение файлов Visual C\+\+](../Topic/Redistributing%20Visual%20C++%20Files.md)