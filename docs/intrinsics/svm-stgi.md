---
title: __svm_stgi | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __svm_stgi
dev_langs:
- C++
helpviewer_keywords:
- __svm_stgi intrinsic
- STGI instruction
ms.assetid: 96488da4-5587-4e99-8674-627a9e51be84
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b4e42643add8c9c6b80d622de8174a8e9379c7a8
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43683088"
---
# <a name="svmstgi"></a>__svm_stgi
**Блок, относящийся только к системам Microsoft**  
  
 Задает флаг глобального прерывания.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void __svm_stgi(void);  
```  
  
## <a name="remarks"></a>Примечания  
 `__svm_stgi` Функция эквивалентна `STGI` инструкции компьютера. Флаг прерывания глобального определяет микропроцессора игнорирует, откладывающий или обрабатывает прерывания из-за события, такие как завершение ввода/вывода, температуры оповещение оборудования или исключение отладки.  
  
 Эта функция поддерживает взаимодействие монитора виртуальной машины узла с гостевой операционной системой и ее приложениями. Дополнительные сведения см. в документе «архитектуре AMD64 для программистов вручную том 2: программирование,» номер 24593, 3.11, версия документа в [AMD corporation](https://developer.amd.com/resources/developer-guides-manuals/) сайта.  
  
## <a name="requirements"></a>Требования  
  
|Встроенная функция|Архитектура|  
|---------------|------------------|  
|`__svm_stgi`|x86, x64|  
  
 **Файл заголовка** \<intrin.h >  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)   
 [__svm_clgi](../intrinsics/svm-clgi.md)