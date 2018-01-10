---
title: "Реализация диалогового | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CSimpleDialog class, implementing dialog boxes in ATL
- dialog boxes, ATL
- CAxDialogImpl class, implementing dialog boxes in ATL
- ATL, dialog boxes
ms.assetid: 478525f2-aa6a-435a-b162-68fc8aa98a8e
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9b3ff0e58623a241160da21266d085753be1c457
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="implementing-a-dialog-box"></a>Реализация диалоговое окно
Существует два способа диалоговое окно добавления в проект ATL: используйте мастер диалоговых окон ATL или добавить ее вручную.  
  
## <a name="adding-a-dialog-box-with-the-atl-dialog-wizard"></a>Добавление диалогового окна с мастер диалоговых окон ATL  
 В [диалоговое окно "Добавление класса"](../ide/add-class-dialog-box.md), выберите объект ATL диалоговое окно на диалоговое окно добавления в проект ATL. Заполните мастер диалоговых окон ATL соответствующим образом и нажмите кнопку **Готово**. Мастер добавляет класс, производный от [CAxDialogImpl](../atl/reference/caxdialogimpl-class.md) в проект. Откройте представление ресурсов из **представление** меню ваше диалоговое окно и дважды щелкните его, чтобы открыть в редакторе ресурсов.  
  
> [!NOTE]
>  Если диалогового окна является производным от `CAxDialogImpl`, он может содержать оба ActiveX и элементов управления Windows. Если вы не хотите издержки, связанные с поддержкой элементов управления ActiveX в классе диалогового окна, используйте [CSimpleDialog](../atl/reference/csimpledialog-class.md) или [CDialogImpl](../atl/reference/cdialogimpl-class.md) вместо него.  
  
 Сообщения и обработчики событий можно добавить классов диалоговых окон из представления классов. Дополнительные сведения см. в разделе [Добавление обработчика сообщения ATL](../atl/adding-an-atl-message-handler.md).  
  
## <a name="adding-a-dialog-box-manually"></a>Добавление диалогового окна вручную  
 Реализация диалогового аналогична реализация окна. Класс наследуется от либо [CAxDialogImpl](../atl/reference/caxdialogimpl-class.md), [CDialogImpl](../atl/reference/cdialogimpl-class.md), или [CSimpleDialog](../atl/reference/csimpledialog-class.md) и объявите [схему сообщений](../atl/message-maps-atl.md) для обработки сообщений. Тем не менее необходимо также указать идентификатор ресурса шаблона диалогового окна в производном классе. Класс должен иметь член данных с именем `IDD` для хранения этого значения.  
  
> [!NOTE]
>  При создании диалоговое окно, используя мастер диалоговых окон ATL, мастер автоматически добавляет `IDD` элемент в качестве `enum` типа.  
  
 `CDialogImpl`позволяет реализовать модального или немодального диалогового окна, элементы управления Windows. `CAxDialogImpl`позволяет реализовать модального или немодального диалогового окна, элементы управления ActiveX и Windows.  
  
 Создание модального диалогового окна, создайте экземпляр вашего `CDialogImpl`-производным (или `CAxDialogImpl`-производного) класса, а затем вызвать [DoModal](../atl/reference/cdialogimpl-class.md#domodal) метод. Чтобы закрыть модальное диалоговое окно, вызовите [EndDialog](../atl/reference/cdialogimpl-class.md#enddialog) метод из обработчика сообщений. Чтобы создать немодального диалогового окна, вызовите [создать](../atl/reference/cdialogimpl-class.md#create) вместо метода `DoModal`. Чтобы окончательно удалить немодального диалогового окна, вызовите [DestroyWindow](../atl/reference/cdialogimpl-class.md#destroywindow).  
  
 Получение событий выполняется автоматически в [CAxDialogImpl](../atl/reference/caxdialogimpl-class.md). Реализовать обработчики сообщений диалоговое окно «», как обработчики в `CWindowImpl`-производного класса. Если возвращаемое значение конкретного сообщения, возвращается как `LRESULT`. Возвращенный `LRESULT` значения сопоставляются с ATL для правильной обработки диспетчером диалоговое окно Windows. Дополнительные сведения см. исходный код для [CDialogImplBaseT::DialogProc](../atl/reference/cdialogimpl-class.md#dialogproc) в atlwin.h.  
  
## <a name="example"></a>Пример  
 Следующий класс реализует диалоговое окно:  
  
 [!code-cpp[NVC_ATL_Windowing#66](../atl/codesnippet/cpp/implementing-a-dialog-box_1.h)]  
  
## <a name="see-also"></a>См. также  
 [Классы окон](../atl/atl-window-classes.md)

