---
title: "Версии AFXDLL | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "afxdll"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AFXDLL - библиотека"
  - "мастера приложений [C++], по умолчанию используется AFXDLL"
  - "DLL-версия MFC [C++]"
  - "MFC [C++], AFXDLL-версия"
  - "библиотеки DLL MFC [C++], динамическая компоновка с библиотекой"
  - "библиотеки MFC [C++], динамическая компоновка"
ms.assetid: c078ae8f-85a9-43cb-9ded-c09ca2c45723
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Версии AFXDLL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Вместо создания приложения статически связываться с объектного кода библиотеки MFC, можно построить приложение использовать одну из библиотек AFXDLL, содержащие MFC в DLL, несколько выполнение приложения могут совместно использовать.  Для таблицы имен AFXDLL см. в разделе [Библиотеки DLL: Соглашения об именовании](../build/naming-conventions-for-mfc-dlls.md).  
  
> [!NOTE]
>  По умолчанию с помощью мастера приложений MFC создает проект AFXDLL.  Чтобы использовать статическое связывание кода MFC вместо этого установите параметр **Использовать MFC в статической библиотеке** в мастере приложений MFC.  Статическое связывание недоступно в Standard Visual C\+\+.  
  
## См. также  
 [Версии библиотек MFC](../mfc/mfc-library-versions.md)