---
title: /MANIFEST (создание манифеста параллельной сборки)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.GenerateManifest
helpviewer_keywords:
- -MANIFEST linker option
- /MANIFEST linker option
- MANIFEST linker option
ms.assetid: 98c52e1e-712c-4f49-b149-4d0a3501b600
ms.openlocfilehash: ea58b43accdd854665fad3b70d7aecbc9eaa0f9e
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69492783"
---
# <a name="manifest-create-side-by-side-assembly-manifest"></a>/MANIFEST (создание манифеста параллельной сборки)

```
/MANIFEST[:{EMBED[,ID=#]|NO}]
```

## <a name="remarks"></a>Примечания

/MANIFEST указывает, что компоновщик должен создать параллельный файл манифеста. Дополнительные сведения о файлах манифеста см. в разделе [Справочник по файлам манифеста](/windows/win32/SbsCs/manifest-files-reference).

Значение по умолчанию —/манифест.

Параметр/MANIFEST: EMBED указывает, что компоновщик должен внедрить файл манифеста в образ как ресурс типа RT_MANIFEST. Необязательный `ID` параметр — это идентификатор ресурса, используемый для манифеста. Для исполняемого файла используйте значение 1. Используйте значение 2 для библиотеки DLL, чтобы разрешить ей указывать частные зависимости. `ID` Если параметр не указан, по умолчанию используется значение 2, если задан параметр/DLL. в противном случае значение по умолчанию равно 1.

Начиная с Visual Studio 2008, файлы манифеста для исполняемых файлов содержат раздел, в котором указаны сведения о контроле учетных записей (UAC). Если указать/MANIFEST, но не [/MANIFESTUAC](manifestuac-embeds-uac-information-in-manifest.md) и [/DLL](dll-build-a-dll.md), в манифест будет вставлен фрагмент UAC по умолчанию с уровнем контроля учетных записей, равным *asInvoker* . Дополнительные сведения об уровнях UAC см. [в разделе/MANIFESTUAC (внедряет сведения о контроле учетных записей в манифесте)](manifestuac-embeds-uac-information-in-manifest.md).

Чтобы изменить поведение UAC по умолчанию, выполните одно из следующих действий.

- Укажите параметр/MANIFESTUAC и задайте требуемое значение для уровня UAC.

- Или укажите параметр/MANIFESTUAC: NO, если не нужно создавать фрагмент UAC в манифесте.

Если не указать/MANIFEST, но указать [/MANIFESTDEPENDENCY](manifestdependency-specify-manifest-dependencies.md) комментарии, то создается файл манифеста. Если указать/MANIFEST: NO, файл манифеста не создается.

Если указать/MANIFEST, имя файла манифеста будет совпадать с именем выходного файла, но с расширением MANIFEST, добавленным к имени файла. Например, если имя выходного файла — MyFile. exe, имя файла манифеста — MyFile. exe. manifest.  Если указать/MANIFESTFILE:*Name*, имя манифеста будет указываться в поле *имя*.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Разверните узел **Свойства конфигурации**.

1. Разверните узел **Компоновщик**.

1. Выберите страницу свойств **файл манифеста** .

1. Измените свойство **создать манифест** .

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

1. См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.GenerateManifest%2A>.

## <a name="see-also"></a>См. также

[Справочник по компоновщику MSVC](linking.md)<br/>
[Параметры компоновщика MSVC](linker-options.md)
