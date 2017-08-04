---
title: "Константы преобразования файлов | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.constants.file
dev_langs:
- C++
helpviewer_keywords:
- translation constants
- file translation [C++], constants
- translation, file translation constants
- translation, constants
- constants [C++], file translation mode
- file translation [C++]
ms.assetid: 49b13bf3-442e-4d19-878b-bd1029fa666a
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: e3005ebe8d36f77a470634b9fdd0003d9b6bb8d5
ms.contentlocale: ru-ru
ms.lasthandoff: 05/18/2017

---
# <a name="file-translation-constants"></a>Константы трансляции файлов
## <a name="syntax"></a>Синтаксис  
  
```  
  
#include <stdio.h>  
```  
  
## <a name="remarks"></a>Примечания  
 Эти константы определяют режим преобразования (**"b"** или **"t"**). Режим содержится в строке, указывающей тип доступа (**"r"**, **"w"**, **"a"**, **"r+"**, **"w+"**, **"a+"**).  
  
 Режимы преобразования приведены ниже:  
  
 **t**  
 Открывает файл в текстовом (преобразованном) режиме. В этом режиме сочетания символов возврата каретки и перевода строки (CR-LF) преобразуются в один символ перевода строки (LF) при вводе, а символы перевода строки преобразуются при выводе в сочетания символов возврата каретки и перевода строки. Кроме того, при вводе символ CTRL+Z интерпретируется как символ конца файла. В файлах, открытых для чтения или чтения/записи, функция `fopen` проверяет наличие CTRL+Z в конце файла и удаляет его, если это возможно. Это делается потому, что использование функций `fseek` и `ftell` для перемещения в файле, который заканчивается символом CTRL+Z, может вызвать неправильное поведение функции `fseek` в области конца файла.  
  
> [!NOTE]
>  Параметр **t** не предусмотрен в стандарте ANSI для функций `fopen` и `freopen`. Это расширение Microsoft и оно не должно использоваться, если требуется совместимость с ANSI.  
  
 **b**  
 Открывает в двоичном (непреобразованном) режиме. Вышеописанные преобразования отключены.  
  
 Если символы **t** или **b** в параметре *mode* не указаны, режим преобразования определяется переменной режима по умолчанию [_fmode](../c-runtime-library/fmode.md). Дополнительные сведения об использовании двоичного и текстового режимов см. в разделе [Файловый ввод-вывод в текстовом и двоичном режиме](../c-runtime-library/text-and-binary-mode-file-i-o.md).  
  
## <a name="see-also"></a>См. также  
 [_fdopen, _wfdopen](../c-runtime-library/reference/fdopen-wfdopen.md)   
 [fopen, _wfopen](../c-runtime-library/reference/fopen-wfopen.md)   
 [freopen, _wfreopen](../c-runtime-library/reference/freopen-wfreopen.md)   
 [_fsopen, _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md)   
 [Глобальные константы](../c-runtime-library/global-constants.md)
