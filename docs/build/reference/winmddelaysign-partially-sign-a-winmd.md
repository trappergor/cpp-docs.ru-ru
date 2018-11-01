---
title: /WINMDDELAYSIGN (частично подпишите файл winmd)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.WINMDDelaySign
ms.assetid: 445cd602-62cb-400a-8e3a-4beb6572724d
ms.openlocfilehash: 367dbe0e638e3748f259f22c1e3536bbd7398272
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50606002"
---
# <a name="winmddelaysign-partially-sign-a-winmd"></a>/WINMDDELAYSIGN (частично подпишите файл winmd)

Включает частичную подпись файла метаданных среды выполнения Windows (.winmd), поместив открытый ключ в файле.

```
/WINMDDELAYSIGN[:NO]
```

## <a name="remarks"></a>Примечания

Напоминает [/delaysign](../../build/reference/delaysign-partially-sign-an-assembly.md) параметра компоновщика, который применяется к winmd-файл. Используйте **параметр/winmddelaysign** Если вы хотите поместить только открытый ключ в файл winmd. По умолчанию компоновщик работает так, как если **/winmddelaysign: no** указаны; то есть он не подписывает файл winmd.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Выберите **компоновщика** папки.

1. Выберите **метаданных Windows** страницу свойств.

1. В **отложенная подпись метаданных Windows** раскрывающемся списке выберите нужный вариант.

## <a name="see-also"></a>См. также

[Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)<br/>
[Параметры компоновщика](../../build/reference/linker-options.md)