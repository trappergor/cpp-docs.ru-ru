---
title: -FS (принудительное синхронных записей PDB) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /FS
dev_langs:
- C++
helpviewer_keywords:
- -FS compiler option [C++]
- /FS compiler option [C++]
ms.assetid: b2caaffe-f6e1-4963-b068-648f06b105e0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b332782cb9bcd929bcd67d4d81b7a7d0259f53cc
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45714601"
---
# <a name="fs-force-synchronous-pdb-writes"></a>/FS (принудительное выполнение синхронных записей PDB)

Принудительно записывает в файл базы данных (PDB) программы, созданные [/ZI](../../build/reference/z7-zi-zi-debug-information-format.md) или [/ZI](../../build/reference/z7-zi-zi-debug-information-format.md)— для сериализации через MSPDBSRV. EXE-ФАЙЛА.

## <a name="syntax"></a>Синтаксис

```
/FS
```

## <a name="remarks"></a>Примечания

По умолчанию когда **/ZI** или **/ZI** указан, компилятор блокирует PDB-файлы для записи сведений о типах и символьную отладочную информацию. Это может значительно снизить время, необходимое компилятору создавать сведения о типе, если количество типов велико. Если другой процесс временно блокирует PDB-файл — например, антивирусной программы — операции записи, компилятор может завершиться ошибкой, и может произойти Неустранимая ошибка. Эта проблема также может происходить, когда несколько копий cl.exe получают доступ к тем же PDB-файл — например, если решение содержит независимые проекты, использующие одну промежуточный каталоги или выходные каталоги и параллельные сборки включены. **/FS** параметр компилятора не позволяет компилятору блокировки PDB-файл и принудительно записывает пройти MSPDBSRV. EXE-файла, который выполняет сериализацию доступа. Это могут делать сборок значительно больше времени, а он не предотвращает всех ошибок, которые могут возникнуть, когда несколько экземпляров cl.exe доступа к PDB-файл, в то же время. Мы рекомендуем изменять решения, чтобы написать независимых проектов для разделения промежуточных и расположений для выходных данных, или которые внесении любого из проектов зависит от другой сборки проекта force сериализации.

[/MP](../../build/reference/mp-build-with-multiple-processes.md) позволяет **/FS** по умолчанию.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Выберите **C/C++** папки.

1. Выберите **командной строки** страницу свойств.

1. Изменить **Дополнительные параметры** свойство `/FS` и выберите **ОК**.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также

[Параметры компилятора](../../build/reference/compiler-options.md)<br/>
[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)