---
title: "Создание настраиваемой кисти (редактор изображений для значков) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- colors [C++], brush
- brushes, colors
- brushes, creating custom
- images [C++], creating custom brushes
- graphics [C++], custom brushes
- custom brushes
ms.assetid: 750881aa-6f47-4de9-8ca6-a7a12afc6383
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 38f376053635708372c09a37aa0810e4305db60a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="creating-a-custom-brush-image-editor-for-icons"></a>Создание настраиваемой кисти (редактор изображений для значков)
Пользовательские кисти представляет собой прямоугольный фрагмент изображения, который выбирается и используется как один из готовых кистей редактора изображений. Все операции, которые можно выполнять на выбор, можно выполнять в настраиваемой кисти.  
  
### <a name="to-create-a-custom-brush-from-a-portion-of-an-image"></a>Создание настраиваемой кисти из части изображения  
  
1.  [Выберите часть изображения](../windows/selecting-an-area-of-an-image-image-editor-for-icons.md) , которую требуется использовать в качестве кисти.  
  
2.  Удерживая **SHIFT** ключа вниз, щелкните в выделенной области и перетащите изображение.  
  
     \- или -  
  
3.  Из **изображения** меню, выберите **использовать выделенную область как кисть**.  
  
     Выделенная область становится пользовательской кисть, которая распределяет цветов в выделенной области изображения. Копирование выделенного фрагмента осталось перетаскивания пути. Медленней, создаются дополнительные копии.  
  
     **Примечание** нажатии кнопки **выделение как кисть** без начала Выбор часть изображения будет использовать всего изображения в качестве кисти. Результат использования пользовательской кисти также зависит от выбранных ли [Выбор прозрачного или непрозрачного фона](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md).  
  
 Точки пользовательской кисти, соответствующие текущему цвету фона, обычно являются прозрачными: они не рисования существующий образ. Это поведение можно изменить, чтобы цвет фона закрашивали существующее изображение.  
  
 Пользовательские кисти как штамп или наборе элементов можно использовать для создания разнообразных специальные эффекты.  
  
#### <a name="to-draw-custom-brush-shapes-in-the-background-color"></a>Для рисования фигур настраиваемой кисти цвет фона  
  
1.  [Выберите прозрачный или непрозрачный фон](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md).  
  
2.  [Задать цвет фона](../windows/selecting-foreground-or-background-colors-image-editor-for-icons.md) цвет, в котором необходимо нарисовать.  
  
3.  Поместите настраиваемой кисти место для рисования.  
  
4.  Щелкните правой кнопкой мыши. Непрозрачные области пользовательской кисти рисуются цвет фона.  
  
#### <a name="to-double-or-halve-the-custom-brush-size"></a>Чтобы дважды увеличить или уменьшить размер настраиваемой кисти  
  
1.  Нажмите клавишу **плюс** (**+**) ключа удвоить размер кисти, или **минус** (**-**) ключа, чтобы сократить его .  
  
#### <a name="to-cancel-the-custom-brush"></a>Чтобы отменить настраиваемой кисти  
  
1.  Нажмите клавишу **ESC** или выберите другой инструмент рисования.  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в классических приложениях](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework.* Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях см. в разделе [Globalizing и локализация приложений .NET Framework](/dotnet/standard/globalization-localization/index).  
  
### <a name="requirements"></a>Требования  
 Нет  
  
## <a name="see-also"></a>См. также  
 [Сочетания клавиш](../windows/accelerator-keys-image-editor-for-icons.md)   
 [Редактирование графических ресурсов](../windows/editing-graphical-resources-image-editor-for-icons.md)   
 [Редактор изображений для значков](../windows/image-editor-for-icons.md)

