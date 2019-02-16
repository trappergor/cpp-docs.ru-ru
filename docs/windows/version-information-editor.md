---
title: Редактор сведений о версии (C++)
ms.date: 02/14/2019
f1_keywords:
- vc.editors.version.F1
- vc.editors.version
helpviewer_keywords:
- Version Information editor [C++], about Version Information editor
- editors, Version Information
- resource editors [C++], Version Information editor
- version information resources [C++]
- resources [C++], editing version information
- languages, version information
- New Version Info Block
- blocks, adding
- resources [C++], adding version information
- version information, adding for languages
- blocks, deleting
- version information, deleting blocks
- resources [C++], deleting version information
- VerQueryValue
- version information, accessing from within programs
- GetFileVersionInfo
- version information
ms.assetid: 772e6f19-f765-4cec-9521-0ad3eeb99f9b
ms.openlocfilehash: 8420feb6ddde116a24bee5333f4ef8f83ff4e0d4
ms.sourcegitcommit: 470de1337035dd33682d935b4b6c6d8b1bdb0bbb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2019
ms.locfileid: "56320475"
---
# <a name="version-information-editor-c"></a>Редактор сведений о версии (C++)

Сведения о версии включают идентификационные данные о компании и продукте, номер версии продукта и уведомление об авторских правах и товарных знаках. С помощью **сведения о версии** редакторе, создавать и поддерживать эти данные, которые хранятся в ресурсе сведений о версии. Ресурс сведений о версии не требуется приложением, но он удобен для сбора сведений, идентифицирующий приложение. Сведения о версии также используются API-интерфейсами настройки.

Ресурс сведений о версии содержит верхний блок и один или несколько нижних блоков: один блок фиксированных сведений вверху и один или несколько блоков сведений о версии внизу (для других языков или кодировок). Верхний блок содержит как редактируемые числовые поля, так и раскрывающиеся списки с вариантами для выбора. Нижние блоки содержат только редактируемые текстовые поля.

> [!NOTE]
> Стандарт Windows разрешает наличие только одного ресурса сведений о версии, который называется VS_VERSION_INFO.

## <a name="how-to"></a>Практическое руководство

**Сведения о версии** редактор позволяет:

### <a name="to-edit-a-string-in-a-version-information-resource"></a>Изменение строки в ресурсе сведений о версии

Выберите элемент один раз, чтобы затем еще раз выберите его, чтобы приступить к редактированию. Внести изменения непосредственно в **сведения о версии** таблицы или в [окно "Свойства"](/visualstudio/ide/reference/properties-window). Внесенные изменения будут отображаться и там, и там.

При редактировании `FILEFLAGS` в **сведения о версии** редактор, вы заметите, нельзя задать **Отладка**, **Private Build**, или **специальные Построение** свойства (в **свойства** окно) для RC-файлов:

- **Сведения о версии** редактор задает **Отладка** свойство с `#ifdef` в сценарии ресурса, на основе `_DEBUG` флага сборки.

- Если `Private Build` ключ имеет **значение** в **сведения о версии** таблицы, соответствующий **Private Build** свойство (в **свойства**  окно) для `FILEFLAGS` ключ будет **True**. Если **Значение** пусто, это свойство будет иметь значение **False**. Аналогичным образом **Special Build** ключ (в **сведения о версии** таблицы) привязывается к **Special Build** свойство для `FILEFLAGS` ключ.

Сведения о последовательности строки в блоке можно отсортировать, щелкнув пункт **ключ** или **значение** заголовки столбцов. В результате сведения автоматически будут отображаться в порядке, заданном сортировкой.

### <a name="to-add-version-information-for-another-language-new-version-info-block"></a>Добавление сведений о версии для другого языка (новый блок сведений о версии)

1. Откройте ресурс сведений о версии, дважды щелкнув его в [представлении ресурсов](../windows/resource-view-window.md).

1. Щелкните правой кнопкой мыши внутри таблицы сведений о версии и выберите в контекстном меню пункт **Создать блок сведений о версии** .

   Эта команда добавляет дополнительный блок сведений в текущий ресурс сведений о версии и открывает его соответствующие свойства в [окне "Свойства"](/visualstudio/ide/reference/properties-window).

1. В окне **Свойства** выберите для нового блока соответствующие язык и кодировку.

### <a name="to-delete-a-version-information-block"></a>Удаление блока сведений о версии

1. Откройте ресурс сведений о версии, дважды щелкнув его значок в [представлении ресурсов](../windows/resource-view-window.md).

1. Щелкните правой кнопкой мыши заголовок удаляемого блока, а затем в контекстном меню выберите команду **Удалить блок сведений о версии** .

   Эта команда удаляет выбранный заголовок и оставляет оставшиеся сведения о версии нетронутыми. Действие нельзя отменить.

### <a name="to-access-version-information-from-within-your-program"></a>Доступ к сведениям о версии из создаваемой программы

Если нужно получить доступ к сведениям о версии из создаваемой программы, используйте функции [GetFileVersionInfo](/windows/desktop/api/winver/nf-winver-getfileversioninfoa) и [VerQueryValue](/windows/desktop/api/winver/nf-winver-verqueryvaluea) .

   > [!NOTE]
   > При использовании **сведения о версии** редактора во многих случаях, щелкнуть правой кнопкой мыши для отображения контекстное меню связанных с ресурсом команд. Например, если выбрана при указании заголовке блока, контекстное меню показано **новый блок сведений о версии** и **удалить блок сведений о версии** команды.

## <a name="requirements"></a>Требования

Win32

## <a name="see-also"></a>См. также

[Редакторы ресурсов](../windows/resource-editors.md)<br/>
[Меню и другие ресурсы](https://msdn.microsoft.com/library/windows/desktop/ms632583.aspx)<br/>
[Сведения о версии (Windows)](https://msdn.microsoft.com/library/windows/desktop/ms646981.aspx)
