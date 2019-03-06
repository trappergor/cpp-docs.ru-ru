---
title: /TLBID (указать идентификатор ресурса для TypeLib)
ms.date: 11/04/2016
f1_keywords:
- /tlbid
- VC.Project.VCLinkerTool.TypeLibraryResourceID
helpviewer_keywords:
- tlb files, specifying resource ID
- -TLBID linker option
- .tlb files, specifying resource ID
- /TLBID linker option
- TLBID linker option
- type libraries, specifying resource ID
ms.assetid: 434b28a2-4656-4d52-ac82-8b18bf486fb2
ms.openlocfilehash: b65ef73e2c7802b960b8480fff83c96fbe869293
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57426476"
---
# <a name="tlbid-specify-resource-id-for-typelib"></a>/TLBID (указать идентификатор ресурса для TypeLib)

```
/TLBID:id
```

## <a name="arguments"></a>Аргументы

*id*<br/>
Заданное пользователем значение для библиотеки типов, созданной компоновщиком. Этот параметр переопределяет идентификатор ресурса по умолчанию 1.

## <a name="remarks"></a>Примечания

При компиляции программы, использующей атрибуты, компоновщик создаст библиотеку типов. Компоновщик назначит идентификатор ресурса 1 к библиотеке типов.

Если этот идентификатор ресурса конфликтует с одним из существующих ресурсов, можно указать другой идентификатор с помощью/TLBID. Диапазон значений, которые можно передать `id` : 1 – 65535.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств проекта Visual C++ параметр](../../ide/working-with-project-properties.md).

1. Нажмите кнопку **компоновщика** папки.

1. Нажмите кнопку **внедренные IDL** страницу свойств.

1. Изменить **идентификатор ресурса TypeLib** свойство.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

1. См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TypeLibraryResourceID%2A>.

## <a name="see-also"></a>См. также

[Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)<br/>
[Параметры компоновщика](../../build/reference/linker-options.md)
