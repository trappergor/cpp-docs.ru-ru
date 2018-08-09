---
title: Задание размера для поле со списком и соответствующего раскрывающегося списка | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.dialog.combo
dev_langs:
- C++
helpviewer_keywords:
- combo boxes, sizing
- controls [C++], sizing
ms.assetid: 51fb53cf-9ddf-4a20-962e-8553938e55ee
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6a22f67bdb0d9d88cd2bb448628734db30f75885
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39643177"
---
# <a name="setting-the-size-of-the-combo-box-and-its-drop-down-list"></a>Задание размера для поля со списком и соответствующего раскрывающегося списка
Поле со списком можно определить размер при добавлении в диалоговом окне. Также можно указать размер поля с раскрывающимся списком.  
  
### <a name="to-size-a-combo-box"></a>Для изменения размера поле со списком  
  
1.  Выберите элемент управления полем со списком в диалоговом окне.  
  
     Изначально активны только маркеры изменения размера вправо и влево.  
  
2.  Используйте маркеры, чтобы задать ширину поля со списком.  
  
 Можно также задать размер по вертикали раскрывающаяся часть поля со списком.  
  
#### <a name="to-set-the-size-of-the-combo-box-drop-down-list"></a>Чтобы задать размер поля со списком поле с раскрывающимся списком  
  
1.  Нажмите кнопку со стрелкой раскрывающегося списка в правой части поля со списком.  
  
     ![Стрелка на поле со списком в проекте MFC](../mfc/media/vccomboboxarrow.gif "vcComboBoxArrow")  
  
     Структура элемента управления для отображения размера поля со списком с развернутой областью раскрывающегося списка.  
  
2.  Используйте нижний маркер изменения размера для изменения начального размера области стрелку раскрывающегося списка.  
  
     ![Поле со списком&#45;изменение размера в проекте MFC](../mfc/media/vccomboboxsizing.gif "vcComboBoxSizing")  
  
3.  Щелкните стрелку раскрывающегося списка, чтобы закрыть область стрелку раскрывающегося списка в поле со списком.  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*. Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях, см. в разделе [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).  
  
## <a name="requirements"></a>Требования  
 Win32  
  
## <a name="see-also"></a>См. также  
 [Добавление значений в поле со списком](../windows/adding-values-to-a-combo-box-control.md)   
 [Элементы управления в диалоговых окнах](../windows/controls-in-dialog-boxes.md)   
 [Элементы управления](../mfc/controls-mfc.md)