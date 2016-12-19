---
title: "Практическое руководство. Сборка не требующих регистрации компонентов COM | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
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
  - "компоненты COM, без регистрации"
ms.assetid: 7e585d6a-0314-45b2-8f1b-cae9ac4df037
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Практическое руководство. Сборка не требующих регистрации компонентов COM
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Компоненты COM, не требующие регистрации, ― это компоненты COM, содержащие встроенные в библиотеки DLL манифесты.  
  
### Встраивание манифеста в компоненты COM  
  
1.  Откройте страницы свойств проекта для компонента COM.  
  
2.  Раскройте узел **Свойства конфигурации**, после чего раскройте узел **Инструмент манифеста**.  
  
3.  Выберите страницу свойств **Ввод и вывод** и задайте для свойства **Встраивать манифест** значение **Да**.  
  
4.  Нажмите кнопку **ОК**.  
  
5.  Постройте решение.  
  
## См. также  
 [Изолированные приложения](http://msdn.microsoft.com/library/aa375190)   
 [Параллельные сборки](_win32_side_by_side_assemblies)   
 [Практическое руководство. Построение изолированных приложений, использующих компоненты СОМ](../Topic/How%20to:%20Build%20Isolated%20Applications%20to%20Consume%20COM%20Components.md)