---
title: Создание настраиваемой кисти (редактор изображений для значков) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- colors [C++], brush
- brushes, colors
- brushes, creating custom
- images [C++], creating custom brushes
- graphics [C++], custom brushes
- custom brushes
ms.assetid: 750881aa-6f47-4de9-8ca6-a7a12afc6383
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bd4a25b208232c8a0923e33156730fc5612219a5
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46388203"
---
# <a name="creating-a-custom-brush-image-editor-for-icons"></a>Создание настраиваемой кисти (редактор изображений для значков)

Настраиваемой кисти является прямоугольного фрагмента изображения, которые получают и использовать как один из **изображение** готовых кистей редактора. Все операции, которые можно выполнять для выделенной области, можно выполнить для пользовательской кисти.

### <a name="to-create-a-custom-brush-from-a-portion-of-an-image"></a>Создание настраиваемой кисти из часть изображения

1. [Выберите часть изображения](../windows/selecting-an-area-of-an-image-image-editor-for-icons.md) , вы хотите использовать в качестве кисти.

2. Удерживая **Shift** ключа вниз, щелкните выделение и перетащите его по изображению.

   \- или -

3. Из **изображение** меню, выберите **использовать выделенную область как кисть**.

   Выделенная область становится настраиваемой кисти, распределяются цветов в выделенной области изображения. Вдоль клоны остается выделенной области. Медленней, создаются дополнительные копии.

   > [!NOTE]
   > Щелкнув **выделение как кисть** без сначала выбрав часть изображения будет использование всего изображения в качестве кисти. В результате применения пользовательской кисти также зависит от того, что вы выбрано [Выбор прозрачного или непрозрачного фона](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md).

Точки пользовательской кисти, соответствующие текущему цвету фона, обычно являются прозрачными: они не закрашивают существующий образ. Это поведение можно изменить таким образом, чтобы цвет фона пикселей маскировать существующий образ.

Пользовательские brush, например метку или набор элементов можно использовать для создания разнообразных специальных эффектов.

### <a name="to-draw-custom-brush-shapes-in-the-background-color"></a>Для рисования фигур настраиваемой кисти в цвет фона

1. [Выберите прозрачный или непрозрачный фон](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md).

2. [Задайте цвет фона](../windows/selecting-foreground-or-background-colors-image-editor-for-icons.md) цвет, в котором необходимо нарисовать.

3. Поместите настраиваемой кисти место для рисования.

4. Щелкните правой кнопкой мыши. Непрозрачные области пользовательской кисти рисуются цвет фона.

### <a name="to-double-or-halve-the-custom-brush-size"></a>Чтобы дважды увеличить или уменьшить размер пользовательской кисти

1. Нажмите клавишу **плюс** (**+**) ключ размера кисти, или **"минус"** (**-**) ключ, чтобы сократить его .

### <a name="to-cancel-the-custom-brush"></a>Чтобы отменить настраиваемой кисти

1. Нажмите клавишу **Esc** или выберите другой инструмент рисования.

Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*. Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях, см. в разделе [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Требования

Нет

## <a name="see-also"></a>См. также

[Сочетания клавиш](../windows/accelerator-keys-image-editor-for-icons.md)<br/>
[Изменение графических ресурсов](../windows/editing-graphical-resources-image-editor-for-icons.md)<br/>
[Редактор изображений для значков](../windows/image-editor-for-icons.md)