---
title: "CUserException Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CUserException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CUserException class"
  - "ошибки [C++], перехват"
  - "исключения, создание"
  - "operations [C++]"
  - "operations [C++], остановка"
  - "создание исключений, stopping user operations"
ms.assetid: 2156ba6d-2cce-415a-9000-6f02c26fcd7d
caps.latest.revision: 23
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CUserException Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Пунктирная, чтобы остановить операции пользователя.  
  
## Синтаксис  
  
```  
class CUserException : public CSimpleException  
```  
  
## Заметки  
 Используйте `CUserException`, когда нужно использовать механизм исключения или catch для приложения исключений. "  Пользователь" в имени класса может быть интерпретировано как "мой пользователь произвел что\-то исключительное, необходимы дополнительные требуется обработать."  
  
 `CUserException` обычно вызывается после вызова глобальной функции `AfxMessageBox` для уведомления пользователя о том, что операция терпела ошибкой.  При написании обработчика исключений, обрабатывайте исключение специально поскольку пользователь обычно уже было уведомить сбоя.  Платформа вызывает это исключение в некоторых случаях.  Для вызова `CUserException` себя, оповестите пользователя и затем вызовите `AfxThrowUserException` глобальной функции.  
  
 В примере, приведенном ниже, функция, содержащие операции, которые могут завершиться ошибкой предупреждения пользователя и вызывают `CUserException`.  При вызове функции перехватывает исключение и его обрабатывают особенно:  
  
 [!code-cpp[NVC_MFCExceptions#24](../../mfc/codesnippet/CPP/cuserexception-class_1.cpp)]  
  
 Дополнительные сведения об использовании `CUserException` см. в статье [Обработка исключений \(MFC\)](../../mfc/exception-handling-in-mfc.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 [CSimpleException](../../mfc/reference/csimpleexception-class.md)  
  
 `CUserException`  
  
## Требования  
 **Заголовок:** afxwin.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CException Class](../../mfc/reference/cexception-class.md)   
 [AfxMessageBox](../Topic/AfxMessageBox.md)   
 [AfxThrowUserException](../Topic/AfxThrowUserException.md)   
 [Инструкции: Создайте мои собственные пользовательские классы исключений?](http://go.microsoft.com/fwlink/?LinkId=128045)