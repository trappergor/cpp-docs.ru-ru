---
title: "Контейнеры элементов управления ActiveX: Использование элементов управления в контейнере без диалоговых окон | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- Create method [MFC], ActiveX controls
- CreateControl method [MFC]
- ActiveX controls [MFC], creating
- ActiveX control containers [MFC], non-dialog containers
- ActiveX control containers [MFC], inserting controls
ms.assetid: 46f195b0-b8ca-4409-8cca-fbfaf2c9ab9f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c380d0a525c2f026054ebae1812450c4d4634c1e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="activex-control-containers-using-controls-in-a-non-dialog-container"></a>Контейнеры элементов управления ActiveX. Использование элементов управления в контейнере без диалоговых окон
В некоторых приложений, таких как SDI или MDI-приложения требуется внедрить элемент управления в окне приложения. **Создать** функции-члена класса-оболочки, вставленные с Visual C++, можно создать экземпляр элемента управления динамически, без необходимости для диалогового окна.  
  
 **Создать** функция-член имеет следующие параметры:  
  
 `lpszWindowName`  
 Указатель на текст, который отображается в свойстве Text или Caption элемента управления (если таковые имеются).  
  
 `dwStyle`  
 Стили Windows. Полный список см. в разделе [CWnd::CreateControl](../mfc/reference/cwnd-class.md#createcontrol).  
  
 `rect`  
 Задает размер и положение элемента управления.  
  
 `pParentWnd`  
 Указывает родительскому окну элемента управления, обычно `CDialog`. Он не должен быть **NULL**.  
  
 `nID`  
 Указывает идентификатор элемента управления и может использоваться в качестве контейнера для ссылки на элемент управления.  
  
 В представлении формы приложения SDI бы один пример использования этой функции для динамического создания элемента управления ActiveX. Затем можно создать экземпляр элемента управления в `WM_CREATE` обработчика приложения.  
  
 В этом примере `CMyView` — это класс основного представления `CCirc` класс-оболочку и круглый H — это заголовок (. H) файл класса-оболочки.  
  
 Реализации этой функции выполняется в четыре этапа.  
  
### <a name="to-dynamically-create-an-activex-control-in-a-non-dialog-window"></a>Для динамического создания элемента управления ActiveX в окне без диалоговых окон  
  
1.  Вставка круглый H в CMYVIEW. H, непосредственно перед `CMyView` определения класса:  
  
     [!code-cpp[NVC_MFC_AxCont#12](../mfc/codesnippet/cpp/activex-control-containers-using-controls-in-a-non-dialog-container_1.h)]  
  
2.  Добавьте переменную-член (типа `CCirc`) в защищенный раздел `CMyView` в CMYVIEW определения класса. H:  
  
     [!code-cpp[NVC_MFC_AxCont#13](../mfc/codesnippet/cpp/activex-control-containers-using-controls-in-a-non-dialog-container_2.h)]  
    [!code-cpp[NVC_MFC_AxCont#14](../mfc/codesnippet/cpp/activex-control-containers-using-controls-in-a-non-dialog-container_3.h)]  
  
3.  Добавить `WM_CREATE` обработчик сообщений для класса `CMyView`.  
  
4.  В функции обработчика `CMyView::OnCreate`, вызовите элемент управления `Create` функцию при помощи **это** указатель в виде родительского окна:  
  
     [!code-cpp[NVC_MFC_AxCont#15](../mfc/codesnippet/cpp/activex-control-containers-using-controls-in-a-non-dialog-container_4.cpp)]  
  
5.  Перестройте проект. Элемент управления Circ создается динамически при каждом создании представления приложения.  
  
## <a name="see-also"></a>См. также  
 [Контейнеры для элементов ActiveX](../mfc/activex-control-containers.md)

