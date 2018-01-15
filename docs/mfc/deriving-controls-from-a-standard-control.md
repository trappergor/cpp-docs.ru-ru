---
title: "Наследование элементов управления от стандартного элемента управления | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- standard controls [MFC], deriving controls from
- common controls [MFC], deriving from
- derived controls
- controls [MFC], derived
- Windows common controls [MFC], deriving from
- standard controls
ms.assetid: a6f84315-7007-4e0e-8576-78be81254802
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2b93bc07fc5ab4680caaa276daaeca86189b8ce5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="deriving-controls-from-a-standard-control"></a>Наследование элементов управления от стандартного элемента управления
Как и в случае с любым [CWnd](../mfc/reference/cwnd-class.md)-производного класса, можно изменить поведение элемента управления нового класса, производного от существующего класса элемента управления.  
  
### <a name="to-create-a-derived-control-class"></a>Чтобы создать класс производного элемента управления  
  
1.  Класс, производный от существующего класса элемента управления и при необходимости переопределить **создать** функция-член, чтобы он предоставляет необходимые аргументы для базового класса **создать** функции.  
  
2.  Предоставляют функции-члены обработчика сообщений и записи схемы сообщений для изменения поведения элемента управления в ответ на определенные сообщения Windows. В разделе [сопоставление сообщений с функциями](../mfc/reference/mapping-messages-to-functions.md).  
  
3.  Предоставляют функции-члены для расширения функциональности элемента управления (необязательно).  
  
 Использование производного элемента управления в диалоговом окне требует дополнительных действий. Типы и положение элементов управления в диалоговом окне обычно задаются в ресурсе шаблона диалогового окна. При создании класса производного элемента управления, невозможно указать его в шаблон диалогового окна, так как компилятор ресурсов ничего не известно о производного класса.  
  
#### <a name="to-place-your-derived-control-in-a-dialog-box"></a>Для размещения элемента управления в диалоговое окно  
  
1.  Объект класса производного элемента управления, внедренный в объявление класса производного диалогового окна.  
  
2.  Переопределить `OnInitDialog` классов диалоговых окон для вызова функции-члена `SubclassDlgItem` функции-члена производного элемента управления.  
  
 `SubclassDlgItem`«динамически подклассов» элемент управления создан из шаблона диалогового окна. Когда элемент управления динамически подклассы, подключения в Windows, обработки некоторых сообщений в приложении и затем передать оставшиеся сообщения на Windows. Дополнительные сведения см. в разделе [SubclassDlgItem](../mfc/reference/cwnd-class.md#subclassdlgitem) функции-члена класса `CWnd` в *Справочник по библиотеке MFC*. В следующем примере показано, как можно написать переопределение `OnInitDialog` для вызова `SubclassDlgItem`:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#3](../mfc/codesnippet/cpp/deriving-controls-from-a-standard-control_1.cpp)]  
  
 Так как производного элемента управления внедрен в класс диалоговых окон, он будет создан при создается диалоговое окно, он будет уничтожен при уничтожении диалоговым окном. Сравнить этот код в примере из [Добавление элементов управления By Рука](../mfc/adding-controls-by-hand.md).  
  
## <a name="see-also"></a>См. также  
 [Создание и использование элементов управления](../mfc/making-and-using-controls.md)   
 [Элементы управления](../mfc/controls-mfc.md)

