---
title: "__svm_clgi | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__svm_clgi"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Инструкция CLGI"
  - "Встроенная функция __svm_clgi"
ms.assetid: 6640f5ab-9472-46f9-a042-e15c4f1ff858
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# __svm_clgi
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Только для систем Microsoft**  
  
 Очищает глобальный пометить прерывания.  
  
## Синтаксис  
  
```  
void __svm_clgi( void );  
```  
  
## Заметки  
 Функция `__svm_clgi` эквивалентна инструкцие на компьютере `CLGI`.  Глобальный пометить прерывания определяет, пропускает ли микропроцессор, откладывать прерывания или обрабатывает события, например из\-за завершения ВВОДА\-ВЫВОДА, аппаратный предупреждение температуры или исключение отладки.  
  
 Эта функция поддерживает взаимодействие монитора виртуальной машины узла с операционной системой для виртуальной машине и своими приложениями.  Дополнительные сведения см. в документе «этом 2 программиста архитектуры AMD64 ручного: Программирование системы,» документ 24593, 3,11, на [корпорация AMD](http://go.microsoft.com/fwlink/?LinkId=23746) сайте.  
  
## Требования  
  
|Встроенный объект|Архитектура|  
|-----------------------|-----------------|  
|`__svm_clgi`|x86, [!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
  
 **Файл заголовка** \<intrin.h\>  
  
## ЭЛЕМЕНТ, относящийся Майкрософт  
  
## См. также  
 [Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)   
 [\_\_svm\_stgi](../intrinsics/svm-stgi.md)