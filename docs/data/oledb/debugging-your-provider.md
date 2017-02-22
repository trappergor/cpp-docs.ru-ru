---
title: "Отладка поставщика | Microsoft Docs"
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
  - "отладка [C++], поставщики"
  - "поставщики OLE DB, отладка"
  - "отладчик Visual C++"
  - "отладчик Visual C++, отладка поставщиков"
ms.assetid: 90d4e7db-06ea-4de0-a7f4-4f3751d50d93
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Отладка поставщика
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Существует два способа отладки поставщика.  
  
-   Поскольку поставщики создаются в процессе, можно создать определенный код потребителя с использованием пользовательских шаблонов OLE DB и перейти к поставщику обычным способом.  
  
-   Можно воспользоваться служебной программой ITEST, поставляемой вместе с Visual C\+\+.  
  
### Использование служебной программы ITEST  
  
1.  Откройте проекта поставщика.  
  
2.  В меню **Проекты** выберите **Параметры**.  
  
3.  В диалоговом окне **Страницы свойств** перейдите на вкладку **Отладка**.  
  
4.  В окне **Исполняемый файл для сеанса отладки** выберите приложение ITEST.  
  
5.  Создайте точки останова и выполните отладку обычным способом.  
  
## См. также  
 [Работа с шаблонами поставщика OLE DB](../../data/oledb/working-with-ole-db-provider-templates.md)