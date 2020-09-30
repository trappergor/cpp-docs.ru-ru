---
title: /IDLOUT (присвоение имен выходным файлам MIDL)
ms.date: 11/04/2016
f1_keywords:
- /idlout
- VC.Project.VCLinkerTool.MergedIDLBaseFileName
helpviewer_keywords:
- MIDL, output file names
- .idl files, path
- MIDL
- /IDLOUT linker option
- IDL files, path
- -IDLOUT linker option
- IDLOUT linker option
ms.assetid: 10d00a6a-85b4-4de1-8732-e422c6931509
ms.openlocfilehash: 8dc26a0564a979c918d1eb1eb85e63e9c73caba0
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2020
ms.locfileid: "91506924"
---
# <a name="idlout-name-midl-output-files"></a>/IDLOUT (присвоение имен выходным файлам MIDL)

```
/IDLOUT:[path\]filename
```

## <a name="parameters"></a>Параметры

*путь*<br/>
Абсолютная или относительная спецификация пути. Указание пути влияет только на расположение IDL-файла; все остальные файлы помещаются в каталог проекта.

*filename*<br/>
Указывает имя IDL-файла, созданного компилятором MIDL. Расширение файла не предполагается. Укажите *filename*. idl, если требуется расширение IDL.

## <a name="remarks"></a>Remarks

Параметр/IDLOUT задает имя и расширение IDL-файла.

Компилятор MIDL вызывается компоновщиком КОМПИЛЯТОРОМ MSVC при связывании проектов, имеющих атрибут [module](../../windows/attributes/module-cpp.md) .

/IDLOUT также указывает имена файлов других выходных файлов, связанных с компилятором MIDL:

- *filename*. tlb

- *имя файла*_p. c

- *имя файла*_i. c

- *filename*. h

*filename* — это параметр, который передается в/идлаут. Если указан [/TLBOUT](tlbout-name-dot-tlb-file.md) , TLB-файл получает имя из/TLBOUT *filename*.

Если не указать ни/IDLOUT, ни/TLBOUT, компоновщик создаст vc70. tlb, vc70. idl, vc70_p. c, vc70_i. c и vc70. h.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Выберите папку **компоновщика**.

1. Щелкните страницу свойств **встроенного IDL** .

1. Измените свойство **имя базового файла IDL слияния** .

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MergedIDLBaseFileName%2A>.

## <a name="see-also"></a>См. также раздел

[Справочник по компоновщику MSVC](linking.md)<br/>
[Параметры компоновщика MSVC](linker-options.md)<br/>
[/IGNOREIDL (не обрабатывать атрибуты в MIDL)](ignoreidl-don-t-process-attributes-into-midl.md)<br/>
[/MIDL (указание параметров командной строки MIDL)](midl-specify-midl-command-line-options.md)<br/>
[Сборка атрибутированной программы](../../windows/attributes/cpp-attributes-com-net.md)
