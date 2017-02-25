---
title: "Implementing a Window with CWindowImpl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CWindowImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL - библиотека, окна"
  - "subclassing ATL window classes"
  - "superclassing, ATL - библиотека"
  - "windows [C++], ATL - библиотека"
  - "windows [C++], subclassing"
  - "windows [C++], superclassing"
ms.assetid: 3fc40550-f1d6-4702-8b7c-4cf682b6a855
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Implementing a Window with CWindowImpl
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Для реализации окно, наследуйте класс от `CWindowImpl`.  В производном классе объявите сопоставления сообщений и функции обработчика сообщений.  Теперь можно использовать класс в другой способ: 3  
  
-   [Создайте окно, основанную на классе нового окна](#_atl_creating_a_window_based_on_a_new_windows_class)  
  
-   [Суперкласс существующий класс Windows](#_atl_superclassing_an_existing_windows_class)  
  
-   [Подкласс существующее окно](#_atl_subclassing_an_existing_window)  
  
##  <a name="_atl_creating_a_window_based_on_a_new_windows_class"></a> Создание окна на основе классе нового окна  
 `CWindowImpl` содержит макрос [DECLARE\_WND\_CLASS](../Topic/DECLARE_WND_CLASS.md) для объявления сведения о классах Windows.  Этот макрос реализует функцию `GetWndClassInfo`, которая использует [CWndClassInfo](../atl/reference/cwndclassinfo-class.md) для получения сведений класса нового окна.  При `CWindowImpl::Create` вызываются этот класс Windows регистрация и новое окно создано.  
  
> [!NOTE]
>  `CWindowImpl` передает **NULL** к макросу `DECLARE_WND_CLASS`, что означает, что библиотека ATL создает имя класса Windows.  Чтобы указать собственное имя, передайте строку в `DECLARE_WND_CLASS` в `CWindowImpl`\- производный класс.  
  
## Пример  
 Ниже приведен пример класса, реализующего окно, основанного на классе нового окна:  
  
 [!code-cpp[NVC_ATL_Windowing#64](../atl/codesnippet/CPP/implementing-a-window-with-cwindowimpl_1.h)]  
  
 Для создания окна, создайте экземпляр `CMyWindow` и затем вызовите метод **Создать**.  
  
> [!NOTE]
>  Чтобы переопределить по умолчанию данные о классах Windows, реализуйте метод `GetWndClassInfo` в производном классе с помощью элементов `CWndClassInfo` к соответствующим значениям.  
  
##  <a name="_atl_superclassing_an_existing_windows_class"></a> Superclassing существующий класс Windows  
 Макрос [DECLARE\_WND\_SUPERCLASS](../Topic/DECLARE_WND_SUPERCLASS.md) позволяет создать поле, которое суперклассы существующий класс Windows.  Укажите этот макрос в `CWindowImpl`\- производный класс.  Как любое другое окно библиотеки ATL сообщения настраиваются сопоставлением сообщения.  
  
 При использовании `DECLARE_WND_SUPERCLASS` класс нового окна будет зарегистрировать.  Этот новый класс будет таким же, что и существующий класс, определяющий, но заменяют процедуру окна с `CWindowImpl::WindowProc` \(или с конкретной функцией, которая переопределяет этот метод\).  
  
## Пример  
 Ниже приведен пример класса, суперклассы стандартный класс правки.  
  
 [!code-cpp[NVC_ATL_Windowing#65](../atl/codesnippet/CPP/implementing-a-window-with-cwindowimpl_2.h)]  
  
 Для создания superclassed окно правка, создайте экземпляр `CMyEdit` и затем вызовите метод **Создать**.  
  
##  <a name="_atl_subclassing_an_existing_window"></a> Subclassing существующее окно  
 В подклассу существующее окно, наследуйте класс от `CWindowImpl` и объявите сопоставление сообщения, например в 2 предыдущих случаях.  Однако следует отметить, что не указаны никакие данные классов Windows, поскольку вы будете подкласс уже существующее окно.  
  
 Вместо вызова **Создать**, вызовите `SubclassWindow` и передайте ему дескриптор к существующему окну требуется подклассу.  После того как окно subclassed будет использовать `CWindowImpl::WindowProc` \(или пользовательскую функцию, которая переопределяет этот метод\) для направления сообщений для сопоставления сообщений.  Наконец subclassed окно удалить из объекта, вызовите `UnsubclassWindow`.  Процедура окна исходной затем будет восстановлена.  
  
## См. также  
 [Implementing a Window](../atl/implementing-a-window.md)