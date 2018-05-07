---
title: Добавление класса из элемента управления ActiveX (Visual C++) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ActiveX controls [C++], adding classes
- classes [C++], creating
ms.assetid: 729fcb37-54b8-44d5-9b4e-50bb16e0eea4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 793adf38da33808371a0df71f671c3e29da75326
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="adding-a-class-from-an-activex-control-visual-c"></a>Добавление класса из элемента управления ActiveX (Visual C++)
Этот мастер используется для создания класса MFC из интерфейса в доступного элемента управления ActiveX. Можно добавить класс MFC для [приложение MFC](../mfc/reference/creating-an-mfc-application.md), [MFC DLL](../mfc/reference/creating-an-mfc-dll-project.md), или [управления MFC ActiveX](../mfc/reference/creating-an-mfc-activex-control.md).  
  
> [!NOTE]
>  Необходимо создать проект MFC с автоматизацией включена Добавление класса из элемента управления ActiveX.  
  
 Элемент управления ActiveX — это компонент для повторного использования программного обеспечения, на основе на компонент объекта модели (COM), который поддерживает широкий набор функциональных возможностей OLE и может быть настроена в соответствии с потребностями многих программного обеспечения. Элементы управления ActiveX предназначены для использования в обычные контейнеры элементов управления ActiveX, а также в веб-страницы в Интернете.  
  
### <a name="to-add-an-mfc-class-from-an-activex-control"></a>Добавление класса MFC из элемента управления ActiveX  
  
1.  В любом **обозревателе решений** или [представление классов](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925), щелкните правой кнопкой мыши имя проекта, к которому требуется добавить класс элементов управления ActiveX.  
  
2.  В контекстном меню щелкните **добавить**, а затем нажмите кнопку **Добавление класса**.  
  
3.  В [Добавление класса](../ide/add-class-dialog-box.md) щелкните в области шаблонов диалогового **класс MFC из элемента управления ActiveX**, а затем нажмите кнопку **откройте** для отображения [добавления классов из ActiveX Мастер управления](../ide/add-class-from-activex-control-wizard.md).  
  
 В мастере можно добавить несколько интерфейсов в элементе управления ActiveX. Аналогично можно создать классы из более чем одного элемента управления ActiveX в одном сеансе мастера.  
  
 Можно добавлять классы из элементов управления ActiveX, зарегистрированных в системе, или можно добавлять классы из элементов управления ActiveX в файлы библиотеки типов (TLB-файл, .olb, DLL, ocx; или .exe) без предварительной регистрации их в своей системе. В разделе [элементов](../mfc/reference/registering-ole-controls.md) Дополнительные сведения о регистрации элементов управления ActiveX.  
  
 Мастер создает класс MFC, производный от [CWnd](../mfc/reference/cwnd-class.md) или [COleDispatchDriver](../mfc/reference/coledispatchdriver-class.md), для каждого интерфейса, добавляемого из выбранного элемента управления ActiveX.  
  
## <a name="see-also"></a>См. также  
 [Элементы управления ActiveX MFC](../mfc/mfc-activex-controls.md)   
 [Введение в модель COM и ATL](../atl/introduction-to-com-and-atl.md)