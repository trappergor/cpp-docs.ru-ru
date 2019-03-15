---
title: Использованием PgoAutoSweep
ms.date: 03/14/2018
f1_keywords:
- PgoAutoSweep
- PogoAutoSweepA
- PogoAutoSweepW
ms.openlocfilehash: 2d9804e5ce90663d44ac389ab4f71d10290e6470
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57827266"
---
# <a name="pgoautosweep"></a>Использованием PgoAutoSweep

`PgoAutoSweep` Сохраняет текущий счетчик данные профиля в файле и затем сбрасывает счетчики. Функция во время профильной оптимизации обучение для записи всех данных профиля из выполняющейся программе PGC-файл для последующего использования в оптимизации сборки.

## <a name="syntax"></a>Синтаксис

```cpp
void PgoAutoSweep(const char* name);    // ANSI/MBCS
void PgoAutoSweep(const wchar_t* name); // UNICODE
```

### <a name="parameters"></a>Параметры

*name*<br/>
Строка, идентифицирующая для сохраненного PGC-файл.

## <a name="remarks"></a>Примечания

Вы можете вызвать `PgoAutoSweep` из приложения, чтобы сохранить и сбросить данные профиля в любой момент во время выполнения приложения. В инструментированную сборку `PgoAutoSweep` записывает текущие данные профилирования, сохраняет его в файле и сбрасывает счетчики профиля. Он является эквивалентом функции [pgosweep](pgosweep.md) команду на определенный момент в исполняемом файле. При оптимизированном построении `PgoAutoSweep` является холостой.

Данные счетчиков сохраненный профиль помещается в файл с именем *base_name*-*имя*! *значение*.pgc, где *base_name* является базовым именем исполняемого файла, *имя* параметр, передаваемый `PgoAutoSweep`, и *значение* — Это уникальное значение, обычно монотонно возрастающее число, чтобы предотвратить конфликты имен файлов.

PGC-файлы, созданные `PgoAutoSweep` должны быть объединены в PGD-файл, используемый для создания оптимизированного исполняемого файла. Можно использовать [pgomgr](pgomgr.md) команду, чтобы выполнить слияние.

Можно передать имя объединенный PGD-файла, компоновщик во время оптимизации сборки с помощью **PGD =**_filename_ аргумент [/useprofile](reference/useprofile.md) параметр компоновщика, или с помощью с помощью устаревших **/PGD** параметр компоновщика. Если вы объединить PGC-файлы в файл с именем *base_name*.pgd, не нужно указать имя файла в командной строке, так как компоновщик выбирает имя файла по умолчанию.

`PgoAutoSweep` Функция поддерживает указанный параметр потокобезопасность при создании инструментированной сборки. Если вы используете параметр по умолчанию или указать **NOEXACT** аргумент [/genprofile или/fastgenprofile]() вызовы параметр компоновщика `PgoAutoSweep` не являются поточно ориентированными. **EXACT** аргумент создает поточно ориентированными и повысить точность, но медленнее, инструментированный исполняемый файл.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|`PgoAutoSweep`|\<pgobootrun.h >|

Исполняемый файл необходимо включить файл pgobootrun.lib в связанные библиотеки. Этот файл включен в установку Visual Studio в каталоге библиотеки VC для каждой поддерживаемой архитектуры.

## <a name="example"></a>Пример

В примере ниже используется `PgoAutoSweep` для создания двух. PGC-файлы в разных точках во время выполнения. Первый содержит данные, описывающие поведение среды выполнения до `count` равно 3, а второй содержит данные, собранные с этого момента до того, как завершение работы приложения.

```cpp
// pgoautosweep.cpp
// Compile by using: cl /c /GL /W4 /EHsc /O2 pgoautosweep.cpp
// Link to instrument: link /LTCG /genprofile pgobootrun.lib pgoautosweep.obj
// Run to generate data: pgoautosweep
// Merge data by using command line pgomgr tool:
// pgomgr /merge pgoautosweep-func1!1.pgc pgoautosweep-func2!1.pgc pgoautosweep.pgd
// Link to optimize: link /LTCG /useprofile pgobootrun.lib pgoautosweep.obj

#include <iostream>
#include <windows.h>
#include <pgobootrun.h>

void func2(int count)
{
    std::cout << "hello from func2 " << count << std::endl;
    Sleep(2000);
}

void func1(int count)
{
    std::cout << "hello from func1 " << count << std::endl;
    Sleep(2000);
}

int main()
{
    int count = 10;
    while (count--)
    {
        if (count < 3)
            func2(count);
        else
        {
            func1(count);
            if (count == 3)
            {
                PgoAutoSweep("func1");
            }
        }
    }
    PgoAutoSweep("func2");
}
```

В командной строке разработчика Скомпилируйте код в файл объекта с помощью следующей команды:

`cl /c /GL /W4 /EHsc /O2 pgoautosweep.cpp`

Затем можно создайте инструментированную сборку для обучения с помощью следующей команды:

`link /LTCG /genprofile pgobootrun.lib pgoautosweep.obj`

Запустите инструментированный исполняемый файл для записи данных для обучения. Выходные данные посредством вызовов к `PgoAutoSweep` сохраняются в файлах с именем использованием pgoautosweep func1! 1.pgc и использованием pgoautosweep func2! 1.pgc. Выходные данные программы должны выглядеть следующим образом, во время выполнения:

```Output
hello from func1 9
hello from func1 8
hello from func1 7
hello from func1 6
hello from func1 5
hello from func1 4
hello from func1 3
hello from func2 2
hello from func2 1
hello from func2 0
```

Слияние сохраненные данные в базу данных обучения профиль, выполнив **pgomgr** команды:

`pgoautosweep-func1!1.pgc pgoautosweep-func2!1.pgc`

Выходные данные этой команды выглядит примерно следующим образом:

```Output
Microsoft (R) Profile Guided Optimization Manager 14.13.26128.0
Copyright (C) Microsoft Corporation. All rights reserved.

Merging pgoautosweep-func1!1.pgc
pgoautosweep-func1!1.pgc: Used  3.8% (22304 / 589824) of total space reserved.  0.0% of the counts were dropped due to overflow.
Merging pgoautosweep-func2!1.pgc
pgoautosweep-func2!1.pgc: Used  3.8% (22424 / 589824) of total space reserved.  0.0% of the counts were dropped due to overflow.
```

Теперь можно использовать для создания при оптимизированном построении этим данным для обучения. Используйте следующую команду для создания оптимизированный исполняемый файл:

`link /LTCG /useprofile pgobootrun.lib pgoautosweep.obj`

```Output
Microsoft (R) Incremental Linker Version 14.13.26128.0
Copyright (C) Microsoft Corporation.  All rights reserved.

Merging pgoautosweep!1.pgc
pgoautosweep!1.pgc: Used  3.9% (22904 / 589824) of total space reserved.  0.0% of the counts were dropped due to overflow.
  Reading PGD file 1: pgoautosweep.pgd
Generating code

0 of 0 ( 0.0%) original invalid call sites were matched.
0 new call sites were added.
294 of 294 (100.00%) profiled functions will be compiled for speed
348 of 1239 inline instances were from dead/cold paths
294 of 294 functions (100.0%) were optimized using profile data
16870 of 16870 instructions (100.0%) were optimized using profile data
Finished generating code
```

## <a name="see-also"></a>См. также

[Профильная оптимизация](profile-guided-optimizations.md)<br/>
[pgosweep](pgosweep.md)<br/>
