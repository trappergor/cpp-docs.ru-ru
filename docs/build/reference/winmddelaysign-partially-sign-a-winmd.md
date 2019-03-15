---
title: /WINMDDELAYSIGN (частично подпишите файл winmd)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.WINMDDelaySign
ms.assetid: 445cd602-62cb-400a-8e3a-4beb6572724d
ms.openlocfilehash: 5e6eab3fbc40543b634f03da826d3bd3477b9623
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57421474"
---
# <a name="winmddelaysign-partially-sign-a-winmd"></a>/WINMDDELAYSIGN (частично подпишите файл winmd)

Включает частичную подпись файла метаданных среды выполнения Windows (.winmd), поместив открытый ключ в файле.

```
/WINMDDELAYSIGN[:NO]
```

## <a name="remarks"></a>Примечания

Напоминает [/delaysign](delaysign-partially-sign-an-assembly.md) параметра компоновщика, который применяется к winmd-файл. Используйте **параметр/winmddelaysign** Если вы хотите поместить только открытый ключ в файл winmd. По умолчанию компоновщик работает так, как если **/winmddelaysign: no** указаны; то есть он не подписывает файл winmd.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств компилятора и собранной задать C++ в Visual Studio](../working-with-project-properties.md).

1. Выберите **компоновщика** папки.

1. Выберите **метаданных Windows** страницу свойств.

1. В **отложенная подпись метаданных Windows** раскрывающемся списке выберите нужный вариант.

## <a name="see-also"></a>См. также

[Справочник по компоновщику MSVC](linking.md)<br/>
[Параметры компоновщика MSVC](linker-options.md)
