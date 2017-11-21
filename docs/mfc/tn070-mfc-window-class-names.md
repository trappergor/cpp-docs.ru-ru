---
title: "TN070: Имена классов окна MFC | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.mfc.classes
dev_langs: C++
helpviewer_keywords:
- window class names [MFC]
- TN070 [MFC]
ms.assetid: 90617912-dd58-4a7c-9082-ced71736d7cd
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6a652d4306e01d15d49ae6f931041d3d5dd9909f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="tn070-mfc-window-class-names"></a>TN070. Имена классов окна MFC
> [!NOTE]
>  Следующее техническое примечание не было обновлено, поскольку сначала оно было включено в электронную документацию. В результате некоторые процедуры и разделы могут быть устаревшими или неверными. Для получения последних сведений рекомендуется выполнить поиск интересующей темы в алфавитном указателе документации в Интернете.  
  
 MFC windows используйте имя динамически созданного класса, которое отражает компоненты окна. MFC создает имена классов динамически для окна фрейма, представления и всплывающие окна, созданный приложением. Диалоговые окна и элементы управления, созданные в приложении MFC иметь имя, предоставленное Windows, для класса окна в вопросе.  
  
 Можно заменить имя динамически предоставленный класс с помощью его переопределения и регистрация класса окна [PreCreateWindow](../mfc/reference/cwnd-class.md#precreatewindow). Их имена классов библиотека MFC предоставляет соответствует ни одной из двух следующих форм:  
  
```  
Afx:%x:%x  
Afx:%x:%x:%x:%x:%x  
```  
  
 Шестнадцатеричные цифры, которые заменяют `%x` символов заполняются на основе данных из [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) структуры. MFC использует этот метод, чтобы несколько классов C++, требующих идентичные **WNDCLASS** структуры могут совместно использовать один зарегистрированный класс. В отличие от большинства простых приложений Win32, MFC приложения имеют только один **WNDPROC**, поэтому можно легко обмениваться **WNDCLASS** структуры, чтобы сэкономить время и память. Подставляемые значения `%x` символов, показанном выше, следующим образом:  
  
- **WNDCLASS.hInstance**  
  
- **WNDCLASS.style**  
  
- **WNDCLASS.hCursor**  
  
- **WNDCLASS.hbrBackground**  
  
- **WNDCLASS.hIcon**  
  
 Первая форма (`Afx:%x:%x`) используется, когда **hCursor**, **hbrBackground**, и **hIcon** все **NULL**.  
  
## <a name="see-also"></a>См. также  
 [Технические примечания по номеру](../mfc/technical-notes-by-number.md)   
 [Технические примечания по категории](../mfc/technical-notes-by-category.md)   
 [TN020. Соглашения об именовании и нумерации идентификаторов](../mfc/tn020-id-naming-and-numbering-conventions.md)

