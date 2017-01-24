---
title: "Классы Managed Package Framework | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Managed Package Framework, вспомогательные классы"
  - "вспомогательные классы управляемых пакетов"
  - "Visual Studio SDK, вспомогательные классы управляемых пакетов"
  - "классы [Visual Studio SDK], Managed Package Framework"
ms.assetid: 15aedcc3-c79a-460b-b620-43223f1ae81e
caps.latest.revision: 24
caps.handback.revision: 24
manager: "douge"
---
# Классы Managed Package Framework
Классы Managed Package Framework \(MPF\) можно использовать для создания пакетов VSPackage с помощью управляемого кода. Они предоставляют реализации по умолчанию для многих интерфейсов VSPackage. Скрывая детали и сложности реализации, MPF позволяет создавать продукты интеграции [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] с минимальным объемом кода.  
  
> [!WARNING]
>  Большинство сборок, содержащих классы MPF, поставляются вместе с Visual Studio SDK. Вы можете загрузить исходный код для MPF для проектов в разделе [Managed Package Framework для проектов](http://mpfproj11.codeplex.com/).  
  
## Пространства имен MPF  
 В следующей таблице перечислены пространства имен MPF, предоставляемые [!INCLUDE[vsipsdk](../mfc/includes/vsipsdk_md.md)].  
  
|Пространство имен|Описание|  
|-----------------------|--------------|  
|<xref:Microsoft.VisualStudio>|Содержит полезные классы для обработки ошибок COM, констант [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] и окон Win32.|  
|<xref:Microsoft.VisualStudio.Package>|Включает оболочки управляемого кода для проектов, редакторов и MSBuild [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)].|  
|<xref:Microsoft.VisualStudio.Shell>|Включает базовые классы MPF, от которых можно производить реализацию многих распространенных объектов Visual Studio.|  
|<xref:Microsoft.VisualStudio.Shell.Design>|Содержит расширения конструктора [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)].|  
|<xref:Microsoft.VisualStudio.Shell.Design.Serialization>|Содержит расширения конструктора сериализации [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)].|  
|<xref:Microsoft.VisualStudio.Shell.Design.Serialization.CodeDom>|Содержит расширения конструктора CodeDom [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)].|  
|<xref:Microsoft.VisualStudio.Shell.Flavor>|Поддерживает подтипы проекта \(также называемые "версиями"\).|  
  
## См. также  
 [Пакеты VSPackage и Managed Package Framework](../Topic/VSPackages%20and%20the%20Managed%20Package%20Framework.md)   
 [С помощью Visual Studio сборки взаимодействия](../Topic/Using%20Visual%20Studio%20Interop%20Assemblies.md)   
 [Пакеты VSPackage и Managed Package Framework](../Topic/VSPackages%20and%20the%20Managed%20Package%20Framework.md)