---
title: "__svm_stgi | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__svm_stgi"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Встроенная функция __svm_stgi"
  - "Инструкция STGI"
ms.assetid: 96488da4-5587-4e99-8674-627a9e51be84
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# __svm_stgi
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Только для систем Microsoft**  
  
 Устанавливает глобальный пометить прерывания.  
  
## Синтаксис  
  
```  
void __svm_stgi(void);  
```  
  
## Заметки  
 Функция `__svm_stgi` эквивалентна инструкцие на компьютере `STGI`.  Глобальный пометить прерывания определяет, пропускает ли микропроцессор, откладывать прерывания или обрабатывает события, например из\-за завершения ВВОДА\-ВЫВОДА, аппаратный предупреждение температуры или исключение отладки.  
  
 Эта функция поддерживает взаимодействие монитора виртуальной машины узла с операционной системой для виртуальной машине и своими приложениями.  Дополнительные сведения см. в документе «этом 2 программиста архитектуры AMD64 ручного: Программирование системы,» документ 24593, 3,11, на [корпорация AMD](http://go.microsoft.com/fwlink/?LinkId=23746) сайте.  
  
## Требования  
  
|Встроенный объект|Архитектура|  
|-----------------------|-----------------|  
|`__svm_stgi`|x86, [!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
  
 **Файл заголовка** \<intrin.h\>  
  
## ЭЛЕМЕНТ, относящийся Майкрософт  
  
## См. также  
 [Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)   
 [\_\_svm\_clgi](../intrinsics/svm-clgi.md)