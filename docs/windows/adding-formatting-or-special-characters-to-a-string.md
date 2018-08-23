---
title: Добавление форматирования или специальных символов в строку | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- special characters, adding to strings
- ASCII characters, adding to strings
- strings [C++], formatting
- strings [C++], special characters
ms.assetid: c40f394a-8b2c-4896-ab30-6922863ddbb5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f3c9623e151dc552ae5a1e5c5da65e62065edf5b
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42602237"
---
# <a name="adding-formatting-or-special-characters-to-a-string"></a>Добавление форматирования или специальных символов в строки

### <a name="to-add-formatting-or-special-characters-to-a-string"></a>Добавление форматирования или специальных символов в строку

1. Откройте таблицу строк, дважды щелкнув его значок в [представление ресурсов](../windows/resource-view-window.md).

   > [!NOTE]
   > Если в проекте еще нет RC-файла, см. раздел [Создание нового файла описания ресурсов](../windows/how-to-create-a-resource-script-file.md).

2. Выберите строку, которую требуется изменить.

3. В [окно "Свойства"](/visualstudio/ide/reference/properties-window), добавьте любой из стандартных escape-последовательности, перечисленные ниже текст в **заголовок** поле и нажмите клавишу **ввод**.

   |Чтобы получить это|Введите это|
   |-----------------|---------------|
   |Новая строка|\n|
   |Возврат каретки|\r|
   |Tab|\t|
   |Обратная косая черта (\\)|\\\|
   |Символ ASCII|\ddd (восьмеричная)|
   |оповещение (колокольчик)|\a|

> [!NOTE]
> **Строка** редактор не поддерживает полный набор символов ASCI ЦЕЛИКОМ. Можно использовать только перечисленных выше.

Сведения о добавлении ресурсов в управляемые проекты (предназначенные среда CLR), см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*. Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Пошаговое руководство: локализация форм Windows Forms](http://msdn.microsoft.com/9a96220d-a19b-4de0-9f48-01e5d82679e5) и [Пошаговое руководство: использование ресурсов для локализации с ASP.NET](http://msdn.microsoft.com/Library/bb4e5b44-e2b0-48ab-bbe9-609fb33900b6).

## <a name="requirements"></a>Требования

Win32

## <a name="see-also"></a>См. также

[Редактор строк](../windows/string-editor.md)  