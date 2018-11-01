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
ms.openlocfilehash: 226deb9e8f7273e122e1b9074d2afca8970fc366
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50508063"
---
# <a name="manifest-create-side-by-side-assembly-manifest"></a>/MANIFEST (создание манифеста параллельной сборки)

```
/MANIFEST[:{EMBED[,ID=#]|NO}]
```

## <a name="remarks"></a>Примечания

/ MANIFEST указывает, что компоновщик должен создать файл манифеста side-by-side. Дополнительные сведения о файлах манифеста см. в разделе [манифеста Справочник по файлам](/windows/desktop/SbsCs/manifest-files-reference).

По умолчанию используется/manifest.

/ Manifest: ВНЕДРЕНИЕ параметр указывает, что компоновщик должен внедрения файл манифеста в образ как ресурс типа RT_MANIFEST. Необязательный `ID` параметр — идентификатор ресурса для использования для манифеста. Используйте значение 1 для исполняемого файла. Используйте значение 2 для библиотеки DLL, включить, то для определения частного зависимостей. Если `ID` параметр не указан, значение по умолчанию — 2, если параметр/DLL имеет значение; в противном случае — значение по умолчанию — 1.

Файлы манифеста для исполняемых файлов, начиная с Visual Studio 2008, содержит раздел, в котором указываются сведения контроля учетных записей (UAC). Если указать/manifest но указать ни [/MANIFESTUAC](../../build/reference/manifestuac-embeds-uac-information-in-manifest.md) , ни [/DLL](../../build/reference/dll-build-a-dll.md), фрагмент UAC по умолчанию, имеющий контроля учетных Записей значением уровня *asInvoker* вставляется в манифест. Дополнительные сведения об уровнях контроля учетных Записей, см. в разделе [/MANIFESTUAC (встраивает контроля учетных Записей в манифест сведений об)](../../build/reference/manifestuac-embeds-uac-information-in-manifest.md).

Чтобы изменить поведение по умолчанию для контроля учетных Записей, выполните одно из следующих:

- Укажите параметр/MANIFESTUAC и задайте уровень контроля учетных Записей нужное значение.

- Или укажите параметр/MANIFESTUAC: No, если вы не хотите создавать фрагмент контроля учетных Записей в манифест.

Если не указать/manifest, но указано [/MANIFESTDEPENDENCY](../../build/reference/manifestdependency-specify-manifest-dependencies.md) комментарии, создается файл манифеста. Файл манифеста не создается, если указать /MANIFEST:NO.

При указании/manifest имя файла манифеста является таким же, как имя файла вывода, но с добавленным к имени файла с расширением MANIFEST. Например если MyFile.exe имени выходного файла, имя файла манифеста является MyFile.exe.manifest.  Если параметр/MANIFESTFILE:*имя*, имя манифеста является то, что указано в *имя*.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Разверните узел **Свойства конфигурации**.

1. Разверните **компоновщика** узла.

1. Выберите **файл манифеста** страницу свойств.

1. Изменить **создать манифест** свойство.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

1. См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.GenerateManifest%2A>.

## <a name="see-also"></a>См. также

[Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)<br/>
[Параметры компоновщика](../../build/reference/linker-options.md)