---
title: Изменение свойств строковый ресурс (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- resource identifiers, string properties
- string tables [C++], changing strings
- strings [C++], properties
ms.assetid: 0a220434-f444-4405-9a64-d28d6b965687
ms.openlocfilehash: efa5f690b18c223c60a68071b335a881633845d5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50450990"
---
# <a name="changing-the-properties-of-a-string-resource-c"></a>Изменение свойств строковый ресурс (C++)

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

Сведения о добавлении ресурсов в управляемые проекты (предназначенные среда CLR), см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*. Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Пошаговое руководство: локализация форм Windows Forms](/previous-versions/visualstudio/visual-studio-2010/y99d1cd3).

## <a name="requirements"></a>Требования

Win32

## <a name="see-also"></a>См. также

[Редактор строк](../windows/string-editor.md)