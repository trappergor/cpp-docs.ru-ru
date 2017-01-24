---
title: "Практическое руководство. Использование GetGlobalService | Microsoft Docs"
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
  - "службы, GetGlobalService"
ms.assetid: 4cdf5ab5-9f09-4caf-9011-2dcb2c62f1b7
caps.latest.revision: 14
caps.handback.revision: 14
manager: "douge"
---
# Практическое руководство. Использование GetGlobalService
Иногда можно вызвать службу из контейнера окна инструментов или элемента управления, который не был установлен или же были расположены с поставщиком услуг, не знает о службе требуется.  Например, можно записывать в журнал действий из элемента управления.  Дополнительные сведения об этих и других сценариях см. в разделе [Практическое руководство: Устранение неполадок служб](../Topic/How%20to:%20Troubleshoot%20Services.md).  
  
 Можно получить большую часть [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] службы, вызвав статическое  <xref:Microsoft.VisualStudio.Shell.Package.GetGlobalService%2A> метод.  
  
 <xref:Microsoft.VisualStudio.Shell.Package.GetGlobalService%2A> полагает в кэшированном поставщике услуг, впервые любому инициализирует из производных VSPackage  <xref:Microsoft.VisualStudio.Shell.Package> распологает.  Необходимо гарантировать, что выполняется это условие или еще быть подготовлены для службы null.  
  
 К счастью, <xref:Microsoft.VisualStudio.Shell.Package.GetGlobalService%2A> правильно работает большая часть времени.  
  
-   Если VSPackage предоставляет известную службу только другое VSPackage, VSPackage, запрашивающий службу расположен до загрузки VSPackage, предоставляющий службу.  
  
-   Если окно инструментов создается VSPackage, VSPackage расположен до того, как окно инструментов создается.  
  
-   Если контейнер элемента управления размещается окном инструментов создать VSPackage, VSPackage позиционируется перед тем, как контейнер элемента управления создан.  
  
### Получить службу из контейнера окна инструментов или элемента управления  
  
-   Вставьте этот код в конструкторе окно инструментов или контейнер элемента управления:  
  
     [!code-vb[UseGetGlobalService#1](../misc/codesnippet/VisualBasic/how-to-use-getglobalservice_1.vb)]
     [!code-cs[UseGetGlobalService#1](../misc/codesnippet/CSharp/how-to-use-getglobalservice_1.cs)]  
  
     Этот код получает службу и приводит его к SVsActivityLog <xref:Microsoft.VisualStudio.Shell.Interop.IVsActivityLog> интерфейс, который можно использовать для записи в журнал действий.  Пример см. в разделе [Практическое руководство: использование журнала действий](../Topic/How%20to:%20Use%20the%20Activity%20Log.md).  
  
## См. также  
 [Практическое руководство: Устранение неполадок служб](../Topic/How%20to:%20Troubleshoot%20Services.md)   
 [Использование и предоставления услуг](../Topic/Using%20and%20Providing%20Services.md)   
 [Основы службы](../Topic/Service%20Essentials.md)