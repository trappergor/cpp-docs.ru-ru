---
title: -ORDER (размещение функций по порядку) | Документация Майкрософт
ms.custom: ''
ms.date: 09/05/2018
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
ms.openlocfilehash: 87fafb0f6eba5130524a373a065fb86ea7eacfc9
ms.sourcegitcommit: d10a2382832373b900b1780e1190ab104175397f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43894516"
---
# <a name="order-put-functions-in-order"></a>/ORDER (размещение функций по порядку)

Укажите порядок ссылок для отдельно упакованные функции (COMDAT).

## <a name="syntax"></a>Синтаксис

> **/ ORDER:\@**<em>имя файла</em>

### <a name="parameters"></a>Параметры

*filename*  
Текстовый файл, указывающее порядок ссылок для функций COMDAT.

## <a name="remarks"></a>Примечания

**/ORDER** параметр компилятора позволяет оптимизировать программы разбиение по страницам, группируя вместе с функциями, он вызывает функцию. Можно также сгруппировать наиболее часто вызываемые функции. Эти методы, известный как *изменение настроек* или *оптимизации подкачки*, увеличить вероятность того, что вызываемая функция находится в памяти, если необходимо и ее не нужно загружать с диска.

При компиляции исходного кода в объектный файл, вы сообщает компилятору, что для помещения каждой функции в отдельном разделе, вызывается *COMDAT*, с помощью [/Gy (включение компоновки на уровне функций)](../../build/reference/gy-enable-function-level-linking.md) компилятора параметр. **/ORDER** параметр компоновщика предписывает компоновщику поместите COMDAT в том порядке, заданы исполняемый образ.

Чтобы указать порядок записей COMDAT, создайте *файла ответов*, текстовый файл со списком каждого COMDAT по имени, по одному в строке, в том порядке, они должны быть помещены компоновщиком. Передайте имя этого файла в виде *filename* параметр **/ORDER** параметр. Для функций C++ COMDAT называется декорированную форму имени функции. Использовать недекорированное имя для функции языка C, `main`, и для функции C++, объявленные как `extern "C"`. Имена функций и декорированные имена чувствительны к регистру. Дополнительные сведения о декорированных именах см. в разделе [декорированные имена](../../build/reference/decorated-names.md).

Чтобы найти декорированные имена в записи COMDAT, используйте [DUMPBIN](../../build/reference/dumpbin-reference.md) инструмента [/SYMBOLS](../../build/reference/symbols.md) параметр на объектный файл. Компоновщик автоматически добавляет символ подчеркивания (**\_**) функции имена в ответе файл, если имя начинается с вопросительным знаком (**?**) или знак ( **\@**). Например, если исходный файл, example.cpp, содержит функции `int cpp_func(int)`, `extern "C" int c_func(int)` и `int main(void)`, команда `DUMPBIN /SYMBOLS example.obj` перечислены эти декорированные имена:

```Output
...
088 00000000 SECT1A notype ()    External     | ?cpp_func@@YAHH@Z (int __cdecl cpp_func(int))
089 00000000 SECT22 notype ()    External     | _c_func
08A 00000000 SECT24 notype ()    External     | _main
...
```

В этом случае укажите имена как `?cpp_func@@YAHH@Z`, `c_func`, и `main` в файле ответов.

Если несколько объектов **/ORDER** параметр появляется в параметры компоновщика, последний указанный вступает в силу.

**/ORDER** параметр отключает инкрементную компоновку. Может появиться предупреждение компоновщика [LNK4075](../../error-messages/tool-errors/linker-tools-warning-lnk4075.md) при указании этого параметра, если включена инкрементная компоновка, или если вы указали [/ZI (добавочное PDB)](../../build/reference/z7-zi-zi-debug-information-format.md) параметр компилятора. Чтобы отключить это предупреждение, можно использовать [/INCREMENTAL: no](../../build/reference/incremental-link-incrementally.md) параметр компоновщика, чтобы завершить работу инкрементную компоновку и использовать [/ZI (создать PDB)](../../build/reference/z7-zi-zi-debug-information-format.md) параметр компилятора для создания PDB-файла без инкрементную компоновку.

> [!NOTE]
> ССЫЛКА не может упорядочивать статические функции, поскольку имена не являются именами открытых символов. Когда **/ORDER** указан, Предупреждение компоновщика [LNK4037](../../error-messages/tool-errors/linker-tools-warning-lnk4037.md) создается для каждого символа в файле ответов заказа, либо статический, либо не найден.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств проекта Visual C++ параметр](../../ide/working-with-project-properties.md).

1. Выберите **свойства конфигурации** > **компоновщика** > **оптимизации** страницу свойств.

1. Изменить **порядок функций** свойство может содержать имя файла ответов.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.FunctionOrder%2A>.

## <a name="see-also"></a>См. также

[Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)  
[Параметры компоновщика](../../build/reference/linker-options.md)