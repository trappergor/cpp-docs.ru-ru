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
ms.openlocfilehash: 7c799f3d44428643bccc2869255ffa4e9d194d70
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69493138"
---
# <a name="allowisolation-manifest-lookup"></a>/ALLOWISOLATION (поиск манифеста)

Задает поведение нахождения файлов манифеста.

## <a name="syntax"></a>Синтаксис

```
/ALLOWISOLATION[:NO]
```

## <a name="remarks"></a>Примечания

**/ALLOWISOLATION: нет** означает, что библиотеки DLL загружены, как если бы манифеста не было, и заставляет `IMAGE_DLLCHARACTERISTICS_NO_ISOLATION` компоновщик установить бит в `DllCharacteristics` поле необязательного заголовка.

**/ALLOWISOLATION** заставляет операционную систему выполнять поиск и загрузку манифеста.

По умолчанию используется **/ALLOWISOLATION** .

Если для исполняемого объекта отключена изоляция, загрузчик Windows не будет пытаться найти манифест приложения для только что созданного процесса. Новый процесс не будет иметь контекста активации по умолчанию, даже если манифест находится внутри исполняемого файла или находится в том же каталоге, что и исполняемый файл с именем <em>Executable-Name</em> **. exe. manifest**.

Дополнительные сведения см. в разделе [Справочник по файлам манифеста](/windows/win32/SbsCs/manifest-files-reference).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Откройте страницу свойств**файл манифеста** **компоновщика** >  **свойств** > конфигурации.

1. Измените значение свойства **Разрешить изоляцию** .

## <a name="see-also"></a>См. также

[Справочник по компоновщику MSVC](linking.md)<br/>
[Параметры компоновщика MSVC](linker-options.md)
