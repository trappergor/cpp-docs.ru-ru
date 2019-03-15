---
title: /ALLOWBIND (запретить привязку DLL)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.PreventDLLBinding
- /allowbind
helpviewer_keywords:
- /ALLOWBIND linker option
- binding DLLs
- preventing DLL binding
- ALLOWBIND linker option
- -ALLOWBIND linker option
- DLLs [C++], preventing binding
ms.assetid: 30e37e24-12e4-407e-988a-39d357403598
ms.openlocfilehash: bd9976e434441d2480386ee6fa3d0315fd8d2ef5
ms.sourcegitcommit: faa42c8a051e746d99dcebe70fd4bbaf3b023ace
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2019
ms.locfileid: "57818847"
---
# <a name="allowbind-prevent-dll-binding"></a>/ALLOWBIND (запретить привязку DLL)

```
/ALLOWBIND[:NO]
```

## <a name="remarks"></a>Примечания

Параметр /ALLOWBIND:NO устанавливает в заголовке библиотеки DLL бит, который указывает программе Bind.exe на то, что привязка образа не допускается. Если DLL имеет цифровую подпись, привязывать ее не следует (при привязке цифровая подпись становится недействительной).

Можно изменить существующую библиотеку DLL для функциональности параметра/ALLOWBIND с [параметра/ALLOWBIND](allowbind.md) параметр программы EDITBIN.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств компилятора и собранной задать C++ в Visual Studio](../working-with-project-properties.md).

1. Разверните **свойства конфигурации**, **компоновщика**и выберите **командной строки**.

1. Введите `/ALLOWBIND:NO` в **Дополнительные параметры**.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также

[Справочник по компоновщику MSVC](linking.md)<br/>
[Параметры компоновщика MSVC](linker-options.md)<br/>
[Функция BindImage](/windows/desktop/api/imagehlp/nf-imagehlp-bindimage)<br/>
[Функция BindImageEx](/windows/desktop/api/imagehlp/nf-imagehlp-bindimageex)
