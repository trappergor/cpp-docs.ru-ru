---
title: Перемещение строки из одного файла ресурса в другой | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- strings [C++], moving between files
- resource script files, moving strings
- string editing, moving strings between resources
- String editor, moving strings between files
ms.assetid: 94f8ee81-9b4c-4788-ba95-68c58db38029
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1bb0c91473e0e3a565bf2a1a7273a35eb3ea5916
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42607030"
---
# <a name="moving-a-string-from-one-resource-file-to-another"></a>Перемещение строки из одного файла ресурса в другой

### <a name="to-move-a-string-from-one-resource-script-file-to-another"></a>Перемещение строки из одного файла скрипта ресурсов в другую

1. Откройте таблицы строк в обоих RC-файлов. (Дополнительные сведения см. в разделе [Просмотр ресурсов в файл скрипта ресурсов за пределами проекта](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md).)

   > [!NOTE]
   > Если в проекте еще нет RC-файла, см. раздел [Создание нового файла описания ресурсов](../windows/how-to-create-a-resource-script-file.md).

2. Щелкните правой кнопкой мыши строку, в которой нужно переместить и выберите **Вырезать** в контекстном меню.

3. Поместите курсор в целевом объекте **редактор строк** окна.

4. В RC-файле, к которому нужно вставить строку, щелкните правой кнопкой мыши и выберите **вставить** в контекстном меню.

   > [!NOTE]
   > Если **идентификатор** или **значение** перемещенной строки конфликтует с существующим **идентификатор** или **значение** в целевом файле, либо **Идентификатор** или **значение** перемещенной строки изменений. Если строка существует с тем же **идентификатор**, **идентификатор** перемещенной строки изменений. Если строка существует с тем же **значение**, **значение** перемещенной строки изменений.

Сведения о добавлении ресурсов в управляемые проекты (предназначенные среда CLR), см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*. Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Пошаговое руководство: локализация форм Windows Forms](http://msdn.microsoft.com/9a96220d-a19b-4de0-9f48-01e5d82679e5) и [Пошаговое руководство: использование ресурсов для локализации с ASP.NET](http://msdn.microsoft.com/Library/bb4e5b44-e2b0-48ab-bbe9-609fb33900b6).

## <a name="requirements"></a>Требования

Win32

## <a name="see-also"></a>См. также

[Редактор строк](../windows/string-editor.md)  
[Файлы ресурсов](../windows/resource-files-visual-studio.md)  
[Настройка макетов окон](/visualstudio/ide/customizing-window-layouts-in-visual-studio)  