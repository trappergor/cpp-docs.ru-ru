---
title: /ALLOWISOLATION (поиск манифеста)
ms.date: 11/04/2016
f1_keywords:
- /ALLOWISOLATION
- VC.Project.VCLinkerTool.AllowIsolation
helpviewer_keywords:
- -ALLOWISOLATION linker option
- /ALLOWISOLATION linker option
ms.assetid: 6d41851e-b3c1-4bdf-beaa-031773089d6f
ms.openlocfilehash: 7b2cb4160a0d25aa65d2c5eb345ba1bc08b1c6b3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50428097"
---
# <a name="allowisolation-manifest-lookup"></a>/ALLOWISOLATION (поиск манифеста)

Задает поведение нахождения файлов манифеста.

## <a name="syntax"></a>Синтаксис

```
/ALLOWISOLATION[:NO]
```

## <a name="remarks"></a>Примечания

**/ALLOWISOLATION:no** указывает библиотеки DLL загружаются так, как если бы манифеста не было и приводит к компоновщику задание бита `IMAGE_DLLCHARACTERISTICS_NO_ISOLATION` бит в необязательном заголовке `DllCharacteristics` поля.

**/ ALLOWISOLATION** вынуждает операционную систему на поиск и загрузку манифеста.

**/ ALLOWISOLATION** используется по умолчанию.

При отключении изоляции для исполняемого файла, загрузчик Windows не будет пытаться найти манифест приложения для нового процесса. Новый процесс не будет контекста активации по умолчанию, даже при наличии манифеста в исполняемый файл или размещено в том же каталоге, что и исполняемый файл с именем <em>имя исполняемого файла</em>**. exe.manifest**.

Дополнительные сведения см. в разделе [манифеста Справочник по файлам](/windows/desktop/SbsCs/manifest-files-reference).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Выберите **свойства конфигурации** > **компоновщика** > **файл манифеста** страницу свойств.

1. Изменить **Разрешить изоляцию** свойство.

## <a name="see-also"></a>См. также

[Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)<br/>
[Параметры компоновщика](../../build/reference/linker-options.md)
