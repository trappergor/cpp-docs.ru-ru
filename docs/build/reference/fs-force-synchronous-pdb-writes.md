---
title: "-FS (принудительное выполнение синхронных записей PDB) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /FS
dev_langs:
- C++
helpviewer_keywords:
- -FS compiler option [C++]
- /FS compiler option [C++]
ms.assetid: b2caaffe-f6e1-4963-b068-648f06b105e0
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cec8aa3d1b3417b6bfcb35757ac4a4a51961e16b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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