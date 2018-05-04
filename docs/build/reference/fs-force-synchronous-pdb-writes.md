---
title: -FS (принудительное выполнение синхронных записей PDB) | Документы Microsoft
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
ms.openlocfilehash: 8565022a77742a1a8c7ed1f243a192d94c8627fb
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="fs-force-synchronous-pdb-writes"></a>/FS (принудительное выполнение синхронных записей PDB)
Обеспечивает записей в файле базы данных (PDB) программы, созданные [/ZI](../../build/reference/z7-zi-zi-debug-information-format.md) или [/ZI](../../build/reference/z7-zi-zi-debug-information-format.md)— для сериализации через MSPDBSRV. EXE-ФАЙЛА.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/FS  
```  
  
## <a name="remarks"></a>Примечания  
 По умолчанию когда **/ZI** или **/ZI** указан, компилятор блокирует PDB-файлы для записи сведений о типах и символьную отладочную информацию. Это может значительно сократить время, затрачиваемое компилятору создавать сведения о типе, если существует большое число типов. Если другой процесс временно блокирует PDB-файл — например, антивирусной программой — записывает компилятор может завершиться ошибкой, и возникает неустранимая ошибка. Эта проблема также может произойти, когда несколько копий cl.exe осуществляют доступ к тот же PDB-файл — например, если решение содержит независимые проекты, использующие одну промежуточные каталоги или выходных каталогов и параллельных сборок включены. **/FS** параметр компилятора запрещает компилятору блокировки PDB-файл и принудительно операции записи направляются через MSPDBSRV. EXE, который выполняет сериализацию доступа. Это может сделать сборок значительно больше времени, и она не предотвращает все ошибки, которые могут возникнуть, когда несколько экземпляров cl.exe доступа к PDB-файл, в то же время. Рекомендуется изменить решение, чтобы записи независимых проектов для разделения промежуточных и расположения вывода, или которые внести одно из проектов зависит от другой сборок проектов force сериализации.  
  
 [/MP](../../build/reference/mp-build-with-multiple-processes.md) позволяет **/FS** по умолчанию.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Выберите **C/C++** папки.  
  
3.  Выберите **командной строки** страницу свойств.  
  
4.  Изменить **Дополнительные параметры** включив `/FS` и выберите **ОК**.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)