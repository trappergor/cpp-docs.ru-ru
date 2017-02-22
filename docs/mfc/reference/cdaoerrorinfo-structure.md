---
title: "Структура CDaoErrorInfo | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDaoErrorInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDaoErrorInfo - структура"
  - "доступ к данным DAO.NET, Коллекция ошибок"
ms.assetid: cd37ef71-b0b3-401d-bc2b-540c9147f532
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# Структура CDaoErrorInfo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Структура `CDaoErrorInfo` содержит сведения о конкретном объекте ошибки \(DAO\) для объектов доступа к данным.  
  
## Синтаксис  
  
```  
  
      struct CDaoErrorInfo  
{  
   long m_lErrorCode;  
   CString m_strSource;  
   CString m_strDescription;  
   CString m_strHelpFile;  
   long m_lHelpContext;  
};  
```  
  
#### Параметры  
 *m\_lErrorCode*  
 Числовой код ошибки DAO.  См. раздел «ошибки Trappable Data Access» в справке DAO.  
  
 *m\_strSource*  
 Имя объекта или приложения, который изначально создают ошибки.  Свойство источника определяет строковое выражение, представляющее объект, который изначально выдал; выражение обычно имя класса объекта.  Дополнительные сведения см. в разделе «свойства источника» в справке DAO.  
  
 *m\_strDescription*  
 Описательная строка, связанная с ошибкой.  Дополнительные сведения см. в разделе «свойство описания» в справке DAO.  
  
 *m\_strHelpFile*  
 Полный путь к файлу справки Microsoft Windows.  Дополнительные сведения см. в разделе «HelpContext, свойства HelpFile» в справке DAO.  
  
 *m\_lHelpContext*  
 Контекстный идентификатор для раздела в файле справки Microsoft Windows.  Дополнительные сведения см. в разделе «HelpContext, свойства HelpFile» в справке DAO.  
  
## Заметки  
 MFC DAO объекты не инкапсулирует ошибки в классе.  Вместо этого класс [CDaoException](../../mfc/reference/cdaoexception-class.md) предоставляет интерфейс для доступа к коллекции ошибок, содержащиеся в объекте **DBEngine**  DAO, объекте, также содержит все рабочие области.  Когда операция MFC DAO создает объект `CDaoException`, в перехвате MFC, заполняет структуру `CDaoErrorInfo` и сохраняет его в элементе [m\_pErrorInfo](../Topic/CDaoException::m_pErrorInfo.md) объекта исключения. \(При выборе вызова DAO непосредственно, пользователь должен самостоятельно вызов функции\-члена [GetErrorInfo](../Topic/CDaoException::GetErrorInfo.md) объекта исключения для заполнения `m_pErrorInfo`\).  
  
 Дополнительные сведения о обработки ошибок DAO см. в статье [Исключения: Исключения баз данных](../../mfc/exceptions-database-exceptions.md).  Дополнительные сведения см. в разделе «объект ошибки» в справке DAO.  
  
 Сведения, функцией\-членом [CDaoException::GetErrorInfo](../Topic/CDaoException::GetErrorInfo.md) хранятся в структуре `CDaoErrorInfo`.  Просмотрите элемент данных [m\_pErrorInfo](../Topic/CDaoException::m_pErrorInfo.md) из объекта `CDaoException`, в перехвате в обработчике исключений или вызов `GetErrorInfo` из объекта `CDaoException`, создаваемые явно для проверки ошибок, которые могут возникнуть во время прямого вызова интерфейсов DAO.  `CDaoErrorInfo` также определяет функции\-члена `Dump` выполняется в режиме построения.  Можно использовать `Dump` сбросить содержимое объекта `CDaoErrorInfo`.  
  
## Требования  
 **Header:** afxdao.h  
  
## См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoException Class](../../mfc/reference/cdaoexception-class.md)