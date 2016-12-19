---
title: "Ошибка MSBuild MSB3119 | Microsoft Docs"
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
  - "GenerateManifest.FileAssociationExtensionMissingLeadDot"
helpviewer_keywords: 
  - "MSB3119"
ms.assetid: 52d68b0e-01d4-436f-a96c-733fd20a8c04
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# Ошибка MSBuild MSB3119
**MSB3119. Расширения для сопоставления файлов должны начинаться с точки \(.\).**  
  
 Эта ошибка происходит, если при настройке сопоставления файлов расширение не начинается с точки \(.\).  
  
### Чтобы исправить эту ошибку  
  
-   Задайте для атрибута [Манифест развертывания ClickOnce](../Topic/ClickOnce%20Deployment%20Manifest.md) `extension` значение, начинающееся с точки \(.\), например, ".doc".  
  
## См. также  
 [Страница публикации в конструкторе проектов](../Topic/Publish%20Page,%20Project%20Designer.md)   
 [Манифест приложения ClickOnce](../Topic/ClickOnce%20Application%20Manifest.md)