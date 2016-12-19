---
title: "Ошибка MSBuild MSB3155 | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "MSBuild.GenerateBootstrapper.ProductNotFound"
helpviewer_keywords: 
  - "MSB3155"
ms.assetid: 59bf2293-ef13-4bb1-8f29-5d6966bbe313
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# Ошибка MSBuild MSB3155
**MSB3155: Элемент "\<пакет\>" не найден в "\<путь\>"**  
  
 Это предупреждение появляется, когда пакет с заданным свойством <xref:Microsoft.Build.Tasks.Deployment.Bootstrapper.Product.ProductCode%2A> не удается найти в кэше загрузчика.  
  
> [!NOTE]
>  Компоненты доступа к данным MDAC больше не включены в качестве пакета загрузчика.  Их можно загрузить с веб\-узла [Центра обновления Майкрософт](http://go.microsoft.com/fwlink/?LinkId=86676).  
  
### Чтобы исправить эту ошибку  
  
-   Удалите пакет из списка пакетов, предназначенных для установки, или добавьте пакет в кэш.  Убедитесь также, что манифест правильно отформатирован с использованием допустимых тегов XML.  
  
## См. также  
 [Справочные сведения о схеме пакетов и продуктов](../Topic/Product%20and%20Package%20Schema%20Reference.md)   
 [Элемент \<PackageFiles\>](../Topic/%3CPackageFiles%3E%20Element%20\(Bootstrapper\).md)   
 [Диалоговое окно «Необходимые компоненты»](../Topic/Prerequisites%20Dialog%20Box.md)   
 [Создание пакетов загрузчика](../Topic/Creating%20Bootstrapper%20Packages.md)