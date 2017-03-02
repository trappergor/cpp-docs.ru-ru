---
title: "Неустранимая ошибка C1128 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1128
dev_langs:
- C++
helpviewer_keywords:
- C1128
ms.assetid: 6f9580fd-ecef-48be-9780-dcf666704279
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 7c70243c6fe3acf50e46c6bdf0880ed713b4b16c
ms.lasthandoff: 02/24/2017

---
# <a name="fatal-error-c1128"></a>Неустранимая ошибка C1128
число секций превышает предел формата объектного файла: компилировать с /bigobj  
  
 OBJ-файле превышено допустимое количество разделов, ограничение формата объектного файла COFF.  
  
 Этого ограничения числа разделов может быть результатом использования [/Gy](../../build/reference/gy-enable-function-level-linking.md) и отладочного построения; **/Gy** функции в собственные разделы COMDAT. В отладочном построении существует раздел сведений об отладке для каждой функции COMDAT.  
  
 C1128 также может возникать, если слишком много встроенных функций.  
  
 Чтобы исправить эту ошибку, разделить исходный файл на несколько файлов исходного кода, выполнить компиляцию без **/Gy**, или выполнить компиляцию с  [ /bigobj (увеличение количества разделов в. OBJ-файл)](../../build/reference/bigobj-increase-number-of-sections-in-dot-obj-file.md).  При компиляции с **/Gy**, необходимо будет указать оптимизации отдельно, поскольку **/O2** и **/O1** применяется **/Gy**.  
  
 Если это возможно Скомпилируйте без отладочной информации.  
  
 Необходимо наличие конкретных экземпляров шаблонов в отдельных файлах исходного кода, а не наличие компилятору выдавать их.  
  
 При переносе кода, C1128 вероятностью возникнет сначала при использовании x64 компилятора и более поздних с x86 компилятора. x64 будет иметь по крайней мере четыре раздела связаны с каждой функцией, компилируемой **/Gy** или встроенной из шаблонов или в класс: код, pdata и сведения об отладке, а возможно xdata.  X86 не pdata.
