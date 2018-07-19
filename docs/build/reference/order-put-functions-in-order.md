---
title: -ORDER (размещение функций по порядку) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.FunctionOrder
- /order
dev_langs:
- C++
helpviewer_keywords:
- ORDER linker option
- -ORDER linker option
- LINK tool [C++], program optimizing
- /ORDER linker option
- LINK tool [C++], swap tuning
- paging, optimizing
ms.assetid: ecf5eb3e-e404-4e86-9a91-4e5ec157261a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: de9b0fb629a1bf984929ec170f05e25e740e9cd5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32378487"
---
# <a name="order-put-functions-in-order"></a>/ORDER (размещение функций по порядку)

Укажите порядок ссылок отдельно упакованных функций (COMDAT).

## <a name="syntax"></a>Синтаксис

>/ ORDER: @*имя файла*

### <a name="parameters"></a>Параметры

*filename*  
Текстовый файл, который определяет порядок ссылок для функций COMDAT.

## <a name="remarks"></a>Примечания

**/ORDER** параметр компилятора позволяет оптимизировать программы разбиение по страницам, группируя функции вместе с функциями, которые она вызывает. Можно также сгруппировать наиболее часто вызываемые функции. Эти методы называются *изменение настроек* или *оптимизации подкачки*, увеличить вероятность того, что вызываемая функция находится в памяти, если необходимо и ее не требуется загружать с диска.

При компиляции исходного кода в объектный файл, сообщает компилятору, что перевод каждой функции в отдельном разделе, вызывается *COMDAT*, с помощью [/Gy (включение компоновки на уровне функций)](../../build/reference/gy-enable-function-level-linking.md) компилятора параметр. **/ORDER** компоновщика предписывает компоновщику поместите COMDAT в исполняемый образ, в том порядке, можно указать.

Чтобы указать порядок записей COMDAT, создайте *файла ответов*, текстовый файл, содержащий каждого COMDAT по имени, по одному в строке, в том порядке, они должны располагаться компоновщиком. Передайте имя этого файла в качестве *filename* параметр **/ORDER** параметр. В функциях C++ COMDAT называется декорированную форму имени функции. Использовать внешнее имя для функции C `main`, и для функции C++, объявленные как `extern "C"`. Имена функций и декорированные имена чувствительны к регистру. Дополнительные сведения о декорированных именах см. в разделе [декорированные имена](../../build/reference/decorated-names.md). 

Чтобы найти декорированные имена в записи COMDAT, используйте [DUMPBIN](../../build/reference/dumpbin-reference.md) инструмента [/SYMBOLS](../../build/reference/symbols.md) параметр на объектный файл. Компоновщик автоматически добавляет символ подчеркивания (\_) функции имена в ответе файл, если имя начинается с вопросительным знаком (?) или знак (@). Например, если исходный файл, example.cpp, содержит функции `int cpp_func(int)`, `extern "C" int c_func(int)` и `int main(void)`, команда `DUMPBIN /SYMBOLS example.obj` перечислены эти декорированные имена:

```Output
...
088 00000000 SECT1A notype ()    External     | ?cpp_func@@YAHH@Z (int __cdecl cpp_func(int))
089 00000000 SECT22 notype ()    External     | _c_func
08A 00000000 SECT24 notype ()    External     | _main
...
```

В этом случае укажите имена как `?cpp_func@@YAHH@Z`, `c_func`, и `main` в файле ответов.

Если несколько объектов **/ORDER** параметр появляется в параметры компоновщика, указанное последним вступает в силу.

**/ORDER** отключает инкрементную компоновку. Может появиться предупреждение компоновщика [LNK4075](../../error-messages/tool-errors/linker-tools-warning-lnk4075.md) при указании этого параметра активна инкрементную компоновку, или если вы указали [/ZI (добавочное PDB)](../../build/reference/z7-zi-zi-debug-information-format.md) параметр компилятора. Чтобы отключить это предупреждение, можно использовать [/INCREMENTAL: no](../../build/reference/incremental-link-incrementally.md) компоновщика отключить инкрементную компоновку и использовать [/ZI (создать PDB)](../../build/reference/z7-zi-zi-debug-information-format.md) параметр компилятора для создания PDB-ФАЙЛ без инкрементную компоновку.

> [!NOTE]
> ССЫЛКА не может упорядочивать статические функции, поскольку имена не являются именами открытых символов. Когда **/ORDER** указан, Предупреждение компоновщика [LNK4037](../../error-messages/tool-errors/linker-tools-warning-lnk4037.md) создается для каждого символа в файле ответов заказа, либо статическими, либо не найден.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [задание свойств проекта Visual C++](../../ide/working-with-project-properties.md).  

1. В разделе **свойства конфигурации**откройте **компоновщика** и выберите **оптимизации** страницу свойств.

1. Изменить **порядок функций** свойство может содержать имя файла ответов.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.FunctionOrder%2A>.

## <a name="see-also"></a>См. также

[Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)  
[Параметры компоновщика](../../build/reference/linker-options.md)