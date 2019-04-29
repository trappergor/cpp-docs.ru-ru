---
title: /ASSEMBLYDEBUG (добавление атрибута DebuggableAttribute)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.AssemblyDebug
- /ASSEMBLYDEBUG
helpviewer_keywords:
- /ASSEMBLYDEBUG linker option
- -ASSEMBLYDEBUG linker option
- ASSEMBLYDEBUG linker option
ms.assetid: 94443af3-470c-41d7-83a0-7434563d7982
ms.openlocfilehash: b9899ea76b7a23a0d09442fca01e7d968c5e8aa6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62273096"
---
# <a name="assemblydebug-add-debuggableattribute"></a>/ASSEMBLYDEBUG (добавление атрибута DebuggableAttribute)

```
/ASSEMBLYDEBUG[:DISABLE]
```

/ Параметр ASSEMBLYDEBUG **DebuggableAttribute** атрибута с отладочные сведения отслеживания и отключается оптимизация JIT. Это аналогично указанию следующий атрибут в источнике:

```
[assembly:Debuggable(true, true)];   // same as /ASSEMBLYDEBUG
```

Добавляет выдает **DebuggableAttribute** атрибута, но отключает отслеживание отладочную информацию и включается оптимизация JIT. Это аналогично указанию следующий атрибут в источнике:

```
[assembly:Debuggable(false, false)];   // same as /ASSEMBLYDEBUG:DISABLE
```

По умолчанию используется, чтобы не выпустить **DebuggableAttribute** атрибута.

DebuggableAttribute также может быть добавлен в сборку непосредственно в исходном коде. Например, примененная к объекту директива

```
[assembly:Debuggable(true, true)];   // same as /ASSEMBLYDEBUG
```

## <a name="remarks"></a>Примечания

Бывает необходимо явно указать, что управляемый образ отлаживаемых. С помощью [/ZI](z7-zi-zi-debug-information-format.md) отдельно не является достаточным.

Доступны следующие параметры компоновщика, которые влияют на создание сборки.

- [/ASSEMBLYLINKRESOURCE](assemblylinkresource-link-to-dotnet-framework-resource.md)

- [/ASSEMBLYMODULE](assemblymodule-add-a-msil-module-to-the-assembly.md)

- [/ASSEMBLYRESOURCE](assemblyresource-embed-a-managed-resource.md)

- [/DELAYSIGN](delaysign-partially-sign-an-assembly.md)

- [/KEYCONTAINER](keycontainer-specify-a-key-container-to-sign-an-assembly.md)

- [/KEYFILE](keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)

- [/NOASSEMBLY](noassembly-create-a-msil-module.md)

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств компилятора и собранной задать C++ в Visual Studio](../working-with-project-properties.md).

1. Нажмите кнопку **компоновщика** папки.

1. Нажмите кнопку **Отладка** страницу свойств.

1. Изменить **отлаживаемая сборка** свойство.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AssemblyDebug%2A>.

## <a name="see-also"></a>См. также

[Справочник по компоновщику MSVC](linking.md)<br/>
[Параметры компоновщика MSVC](linker-options.md)
