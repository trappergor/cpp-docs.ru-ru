---
title: Стили полей со списками | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CBS_LOWERCASE
- CBS_SORT
- CBS_OWNERDRAWVARIABLE
- CBS_OEMCONVERT
- CBS_AUTOHSCROLL
- CBS_NOINTEGRALHEIGHT
- CBS_SIMPLE
- CBS_DROPDOWNLIST
- CBS_DROPDOWN
- CBS_UPPERCASE
- CBS_HASSTRINGS
- CBS_DISABLENOSCROLL
- CBS_OWNERDRAWFIXED
dev_langs:
- C++
helpviewer_keywords:
- CBS_OWNERDRAWVARIABLE constant [MFC]
- CBS_NOINTEGRALHEIGHT constant [MFC]
- CBS_SIMPLE constant [MFC]
- CBS_AUTOHSCROLL constant [MFC]
- CBS_OEMCONVERT constant [MFC]
- CBS_DISABLENOSCROLL constant [MFC]
- CBS_HASSTRINGS constant [MFC]
- CBS_LOWERCASE constant [MFC]
- CBS_SORT constant [MFC]
- CBS_DROPDOWN constant [MFC]
- CBS_OWNERDRAWFIXED constant [MFC]
- combo boxes [MFC], styles
- CBS_UPPERCASE constant [MFC]
- CBS_DROPDOWNLIST constant
ms.assetid: d21a5023-e6a2-495b-a6bd-010a515cbc63
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9ec15f483d9a613e77ad07b6f7f306e84099bced
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="combo-box-styles"></a>Стили полей со списками
В MFC доступны перечисленные далее стили полей со списками.  
  
-   **CBS_AUTOHSCROLL** Автоматическая прокрутка текста в элементе управления "Поле ввода" вправо при вводе символа в конце строки. Если этот стиль не задан, допускается только текст, который умещается в прямоугольной области.  
  
-   **CBS_DISABLENOSCROLL** Если в списке содержится недостаточно элементов для прокрутки, в нем отображается отключенная вертикальная полоса прокрутки. Если этот стиль не задан, полоса прокрутки будет скрыта при недостаточном количестве элементов в списке.  
  
-   **CBS_DROPDOWN** Этот стиль аналогичен **CBS_SIMPLE**, за исключением того, что список отображается только после выбора значка рядом с элементом управления "Поле ввода".  
  
-   **CBS_DROPDOWNLIST** Этот стиль аналогичен **CBS_DROPDOWN**, за исключением того, что элемент управления "Поле ввода" заменяется элементом статического текста, который отображает текущее выделение в поле со списком.  
  
-   **CBS_HASSTRINGS** Рисуемое владельцем поле со списком содержит элементы, которые являются строками. Поле со списком поддерживает память и указатели для строк, поэтому приложение может использовать функцию-член `GetText` для получения текста для определенного элемента.  
  
-   **CBS_LOWERCASE** Преобразует в нижний регистр весь текст в поле выбора и в списке.  
  
-   **CBS_NOINTEGRALHEIGHT** Указывает, что размер поля со списком точно соответствует размеру, заданному приложением при создании поля со списком. Как правило, в Windows размер поля со списком определяется так, чтобы в избежать частичного отображения элементов.  
  
-   **CBS_OEMCONVERT** Текст, введенный в элементе управления полем со списком, преобразуется из набора символов ANSI в набор символов OEM и затем обратно в формат ANSI. Это гарантирует правильное преобразование символов, когда приложение вызывает функцию Windows `AnsiToOem` для преобразования строки ANSI в поле со списком в символы OEM. Этот стиль особенно полезен для полей со списком, содержащих имена файлов, и применяется только к полям со списком, созданным с помощью стилей **CBS_SIMPLE** или **CBS_DROPDOWN** .  
  
-   **CBS_OWNERDRAWFIXED** Владелец списка отвечает за рисование его содержимого. Все элементы в списке имеют одинаковую высоту.  
  
-   **CBS_OWNERDRAWVARIABLE** Владелец списка отвечает за рисование его содержимого. Все элементы в списке имеют разную высоту.  
  
-   **CBS_SIMPLE** Список отображается всегда. Текущее выделение в списке отображается в элементе управления "Поле ввода".  
  
-   **CBS_SORT** Автоматически сортирует строки, вводимые в список.  
  
-   **CBS_UPPERCASE** Преобразует в верхний регистр весь текст в поле выбора и в списке.  
  
## <a name="see-also"></a>См. также  
 [Стили, используемые MFC](../../mfc/reference/styles-used-by-mfc.md)   
 [CComboBox::Create] (ccombobox class.md #ccombobox__create   



