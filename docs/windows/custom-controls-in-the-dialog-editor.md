---
title: "Пользовательские элементы управления в редакторе диалоговых окон | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: Custom Control
dev_langs: C++
helpviewer_keywords:
- controls [C++], templates
- custom controls [Visual Studio], dialog boxes
- custom controls [Visual Studio]
- dialog box controls, custom (user) controls
- Dialog editor, custom controls
ms.assetid: f494b314-4000-4bbe-bbd0-4b18fb71ede1
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c507f4d252100055d4ed7f24e9c407bf8edb82d0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="custom-controls-in-the-dialog-editor"></a>Пользовательские элементы управления в редакторе диалогов
Редактор диалоговых окон позволяет использовать существующие «custom» или «пользователь» элементов управления в шаблон диалогового окна.  
  
> [!NOTE]
>  Пользовательские элементы управления в этом смысле являются не следует путать с элементами управления ActiveX. Элементы управления ActiveX иногда называют пользовательскими элементами управления OLE. Кроме того не следует путать эти элементы управления с пользовательскими элементами управления в Windows.  
  
 Эта функция предназначена для позволяют использовать элементы управления, не предоставляемые Windows. Во время выполнения элемент управления связан с классом Windows (отличным от класса C++). Чтобы установить любой элемент управления, такие как статический элемент управления диалогового окна является более общий способ выполнения той же задачи. Затем во время выполнения, в [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) работать, удалите этот элемент управления и замените его собственный пользовательский элемент управления.  
  
 Это техника устарела. В настоящее время рекомендуется в большинстве случаев для записи в элементе управления ActiveX или подкласс общих элементов управления Windows.  
  
 Для этих пользовательских элементов управления ограничены:  
  
-   Настройка расположения в диалоговом окне.  
  
-   Вводить заголовок.  
  
-   Идентифицирующее имя класса элемента управления Windows (код приложения должен зарегистрировать элемент управления с таким именем).  
  
-   Введите 32-разрядное шестнадцатеричное значение, которое задает стиль элемента управления.  
  
-   Установка расширенного стиля.  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в классических приложениях](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework.* Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях см. в разделе [Globalizing и локализация приложений .NET Framework](/dotnet/standard/globalization-localization/index).  
  
## <a name="requirements"></a>Требования  
 Win32  
  
## <a name="see-also"></a>См. также  
 [Элементы управления в диалоговых окнах](../windows/controls-in-dialog-boxes.md)   
 [Элементы управления](../mfc/controls-mfc.md)

