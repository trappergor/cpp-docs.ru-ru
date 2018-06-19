---
title: 'Элементы управления ActiveX MFC: Создание сервера автоматизации | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Automation servers [MFC], MFC ActiveX controls
- ActiveX controls [MFC], Automation server
- MFC ActiveX controls [MFC], Automation server
ms.assetid: e0c24ed2-d61c-49ad-a4fa-4e1098d1d39b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 617d84b8603467da74b21be8c2bfb2e6cb418f7b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33346767"
---
# <a name="mfc-activex-controls-creating-an-automation-server"></a>Элементы управления ActiveX в MFC. Создание сервера автоматизации
Элемент управления MFC ActiveX можно разрабатывать как сервера автоматизации для программного включения этого элемента управления в другом приложении и вызов методов в элементе управления из приложения. Такой элемент управления по-прежнему доступен для размещения в контейнере элементов управления ActiveX.  
  
### <a name="to-create-a-control-as-an-automation-server"></a>Создание элемента управления как сервера автоматизации  
  
1.  [Создание](../mfc/reference/mfc-activex-control-wizard.md) элемента управления.  
  
2.  [Добавьте методы](../mfc/mfc-activex-controls-methods.md).  
  
3.  Переопределить [IsInvokeAllowed](../mfc/reference/colecontrol-class.md#isinvokeallowed). Дополнительные сведения см. в статье базы знаний Q146120.  
  
4.  Создать элемент управления.  
  
### <a name="to-programmatically-access-the-methods-in-an-automation-server"></a>Для программного доступа к методам в сервер автоматизации  
  
1.  Создание приложения, например, [MFC exe](../mfc/reference/mfc-application-wizard.md).  
  
2.  В начале `InitInstance` функционировать, добавьте следующую строку:  
  
     [!code-cpp[NVC_MFC_AxCont#17](../mfc/codesnippet/cpp/mfc-activex-controls-creating-an-automation-server_1.cpp)]  
  
3.  В представлении классов щелкните правой кнопкой мыши узел проекта и выберите **добавления классов из typelib** импорт библиотеки типов.  
  
     Файлы с расширением CPP и .h расширения имени файла будет добавить в проект.  
  
4.  В файле заголовка класса, где будет вызываться один или несколько методов в элементе управления ActiveX, добавьте следующую строку: `#include filename.h`, где имя файла — это имя файла заголовка, который был создан при импорте библиотеки типов.  
  
5.  В функции, местом вызова метода в элементе управления ActiveX добавьте код, который создает объект класса-оболочки элемента управления и создать объект ActiveX. Например, следующий код MFC создает `CCirc` возвращает свойство заголовка элемента управления и отображает результат, при нажатии кнопки «ОК» в диалоговом окне:  
  
     [!code-cpp[NVC_MFC_AxCont#18](../mfc/codesnippet/cpp/mfc-activex-controls-creating-an-automation-server_2.cpp)]  
  
 Если после использования в приложении можно добавить методы в элемент управления ActiveX, можно начать использовать последнюю версию элемента управления в приложении, удалив файлы, которые были созданы при импорте библиотеки типов. Затем импортируйте библиотеку типов.  
  
## <a name="see-also"></a>См. также  
 [Элементы ActiveX библиотеки MFC](../mfc/mfc-activex-controls.md)

