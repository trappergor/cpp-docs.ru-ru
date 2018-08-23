---
title: Изменение свойств строки | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- resource identifiers, string properties
- string tables, changing strings
- strings [C++], properties
ms.assetid: 0a220434-f444-4405-9a64-d28d6b965687
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c30acc25403e2dde3c829f3efd912cf9ba69e5e0
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42609141"
---
# <a name="changing-the-properties-of-a-string"></a>Изменение свойств строки

### <a name="to-change-a-string-or-its-identifier"></a>Чтобы изменить строку или идентификатору

1. Откройте таблицу строк, дважды щелкнув его значок в [представление ресурсов](../windows/resource-view-window.md).

   > [!NOTE]
   > Если в проекте еще нет RC-файла, см. раздел [Создание нового файла описания ресурсов](../windows/how-to-create-a-resource-script-file.md).

2. Выберите строку, в которой нужно изменить и дважды щелкните **идентификатор**, **значение**, или **заголовок** столбца. Теперь вы можете:

   - Выберите **идентификатор** из **раскрывающегося списка ИД** списка или введите `ID` непосредственно в нужное место.

   - Введите другой номер в **значение** столбца.

   - Ввести изменения в **заголовок** столбца.

        > [!NOTE]
        >  Можно также изменить свойства строки в [окно "Свойства"](/visualstudio/ide/reference/properties-window).

Сведения о добавлении ресурсов в управляемые проекты (предназначенные среда CLR), см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*. Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Пошаговое руководство: локализация форм Windows Forms](http://msdn.microsoft.com/9a96220d-a19b-4de0-9f48-01e5d82679e5) и [Пошаговое руководство: использование ресурсов для локализации с ASP.NET](http://msdn.microsoft.com/Library/bb4e5b44-e2b0-48ab-bbe9-609fb33900b6).

## <a name="requirements"></a>Требования

Win32

## <a name="see-also"></a>См. также

[Редактор строк](../windows/string-editor.md)  