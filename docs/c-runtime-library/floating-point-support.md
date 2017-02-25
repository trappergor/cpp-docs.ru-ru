---
title: "Поддержка чисел с плавающей запятой | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.math"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "числа с плавающей запятой"
  - "числа с плавающей запятой, математические подпрограммы"
  - "математические подпрограммы"
ms.assetid: e4fcaf69-5c8e-4854-a9bb-1f412042131e
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# Поддержка чисел с плавающей запятой
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Многие функции библиотеки времени выполнения \(Майкрософт\) требуют, чтобы числа с плавающей запятой поддерживались математическим сопроцессором или библиотеками чисел с плавающей запятой компьютера.  Функции для поддержки чисел с плавающей запятой загружаются только при необходимости.  
  
 При использовании описателя типа с плавающей запятой в строке формата вызова функции в семействе `printf` или `scanf` необходимо указать значение с плавающей запятой или указатель на такое значение в списке аргументов, чтобы уведомить компилятор о необходимости поддержки чисел с плавающей запятой.  
  
 Примеры кода, демонстрирующие обработку исключений чисел с плавающей запятой, см. в разделе [\_fpieee\_flt](../c-runtime-library/reference/fpieee-flt.md).  
  
 Точность вычислений с плавающей запятой для промежуточных значений контролируется функциями [\_control87, \_controlfp, \_\_control87\_2](../Topic/_control87,%20_controlfp,%20__control87_2.md).  По умолчанию для элемента управления точностью `_controlfp` задано значение 53 бита \(\_PC\_53\).  Связывание с помощью FP10.OBJ заменяет значение по умолчанию значением 64 бита \(\_PC\_64\).  В командной строке компоновщика FP10.OBJ должен стоять перед LIBC.LIB, LIBCMT.LIB или MSVCRT.LIB.  
  
### Функции с плавающей запятой  
  
|Подпрограмма|Применение|Эквивалент .NET Framework|  
|------------------|----------------|-------------------------------|  
|[abs](../Topic/abs.md)|Возвращение абсолютного значения `int`|[\<caps:sentence id\="tgt14" sentenceid\="9594ba199e25e9de6b463c8efc9fbe95" class\="tgtSentence"\>System::Math::Abs\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.math.abs.aspx)|  
|[acos, acosf](../c-runtime-library/reference/acos-acosf-acosl.md)|Вычисление арккосинуса|[\<caps:sentence id\="tgt17" sentenceid\="954a441495360a1fa8b0170297b2ff38" class\="tgtSentence"\>System::Math::Acos\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.math.acos.aspx)|  
|[asin, asinf](../c-runtime-library/reference/asin-asinf-asinl.md)|Вычисление арксинуса|[\<caps:sentence id\="tgt20" sentenceid\="313917cde9698a0924536719f5bece25" class\="tgtSentence"\>System::Math::Asin\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.math.asin.aspx)|  
|[atan, atanf, atan2, atan2f](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)|Вычисление арктангенса|[System::Math::Atan](https://msdn.microsoft.com/en-us/library/system.math.atan.aspx), [System::Math::Atan2](https://msdn.microsoft.com/en-us/library/system.math.atan2.aspx)|  
|[atof, \_atof\_l, \_wtof, \_wtof\_l](../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)|Преобразование строки символов в значение двойной точности с плавающей запятой|[System::Convert::ToSingle](https://msdn.microsoft.com/en-us/library/system.convert.tosingle.aspx), [System::Convert::ToDouble](https://msdn.microsoft.com/en-us/library/system.convert.todouble.aspx)|  
|[Функции Бесселя](../c-runtime-library/reference/bessel-functions-j0-j1-jn-y0-y1-yn.md)|Вычисление функций Бесселя `_j0`, `_j1`, `_jn`, `_y0`, `_y1`, `_yn`|Неприменимо.  Для вызова стандартной функции C используйте `PInvoke`.  Для получения дополнительной информации см. [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_cabs](../Topic/_cabs.md)|Нахождение абсолютного значения сложного числа|Неприменимо.|  
|[cbrt](../c-runtime-library/reference/cbrt-cbrtf-cbrtl.md)|Вычисление кубического корня|Неприменимо.|  
|[ceil, ceilf](../c-runtime-library/reference/ceil-ceilf-ceill.md)|Нахождение верхней целой части целого числа|[\<caps:sentence id\="tgt39" sentenceid\="656009d71fb974368bded363746de018" class\="tgtSentence"\>System::Math::Ceiling\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.math.ceiling.aspx)|  
|[\_chgsign, \_chgsignf, \_chgsignl](../c-runtime-library/reference/chgsign-chgsignf-chgsignl.md)|Изменение знака числа двойной точности с плавающей запятой или аргумента числа двойной точности с плавающей запятой long double|Неприменимо.|  
|[\_clear87, \_clearfp](../c-runtime-library/reference/clear87-clearfp.md)|Получение и сброс слова состояния числа с плавающей запятой|Неприменимо.|  
|[\_control87, \_controlfp, \_\_control87\_2](../Topic/_control87,%20_controlfp,%20__control87_2.md), [\_controlfp\_s](../c-runtime-library/reference/controlfp-s.md)|Получение старого управляющего слова числа с плавающей запятой и задание нового значения управляющего слова|Неприменимо.|  
|[copysign, copysignf, copysignl, \_copysign, \_copysignf, \_copysignl](../c-runtime-library/reference/copysign-copysignf-copysignl-copysign-copysignf-copysignl.md)|Возвращение одного значения со знаком другого|Неприменимо.|  
|[cos, cosf, cosh, coshf](../c-runtime-library/reference/cos-cosf-cosl-cosh-coshf-coshl.md)|Вычисление косинуса|[System::Math::Cos](https://msdn.microsoft.com/en-us/library/system.math.cos.aspx), [System::Math::Cosh](https://msdn.microsoft.com/en-us/library/system.math.cosh.aspx)|  
|[difftime](../c-runtime-library/reference/difftime-difftime32-difftime64.md)|Вычисление разницы между двумя указанными значениями времени|[\<caps:sentence id\="tgt54" sentenceid\="5f4f365a3cd7f368db2f6ce31b797fdf" class\="tgtSentence"\>System::DateTime::Subtract\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.datetime.subtract.aspx)|  
|[div](../c-runtime-library/reference/div.md)|Деление одного целого числа на другое, возврат частного и остатка|Неприменимо.|  
|[\_ecvt](../c-runtime-library/reference/ecvt.md), [\_ecvt\_s](../Topic/_ecvt_s.md)|Преобразование `double` в строку символов указанной длины|[\<caps:sentence id\="tgt60" sentenceid\="ed8e24ad5c647dc4efa4fbe1e9bbc5e3" class\="tgtSentence"\>System::Convert::ToString\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.convert.tostring.aspx)|  
|[exp, expf](../c-runtime-library/reference/exp-expf.md)|Вычисление экспоненциальной функции|[\<caps:sentence id\="tgt63" sentenceid\="81a65df6ac66cdc4a4b12c2f7e555487" class\="tgtSentence"\>System::Math::Exp\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.math.exp.aspx)|  
|[fabs, fabsf](../c-runtime-library/reference/fabs-fabsf-fabsl.md)|Нахождение абсолютного значения|[\<caps:sentence id\="tgt66" sentenceid\="9594ba199e25e9de6b463c8efc9fbe95" class\="tgtSentence"\>System::Math::Abs\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.math.abs.aspx)|  
|[\_fcvt](../Topic/_fcvt.md), [\_fcvt\_s](../c-runtime-library/reference/fcvt-s.md)|Преобразование `double` в строку, имеющую заданное число цифр дробной части|[\<caps:sentence id\="tgt69" sentenceid\="ed8e24ad5c647dc4efa4fbe1e9bbc5e3" class\="tgtSentence"\>System::Convert::ToString\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.convert.tostring.aspx)|  
|[\_finite](../c-runtime-library/reference/finite-finitef.md)|Определение конечности данного числа двойной точности с плавающей запятой|[\<caps:sentence id\="tgt72" sentenceid\="8d081c50adeda3dde4cebab81a0b3583" class\="tgtSentence"\>System::Double::IsInfinity\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.double.isinfinity.aspx)|  
|[floor, floorf](../c-runtime-library/reference/floor-floorf-floorl.md)|Нахождение самого большого целого числа, которое меньше или равно аргументу|[\<caps:sentence id\="tgt75" sentenceid\="609db9ab0433b647d5350d3b965d70f9" class\="tgtSentence"\>System::Math::Floor\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.math.floor.aspx)|  
|[fmod, fmodf](../Topic/fmod,%20fmodf.md)|Нахождение остатка с плавающей запятой|[\<caps:sentence id\="tgt78" sentenceid\="127a04426267ccb17fb4b566ad56de9c" class\="tgtSentence"\>System::Math::IEEERemainder\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.math.ieeeremainder.aspx)|  
|[\_fpclass](../c-runtime-library/reference/fpclass-fpclassf.md)|Возвращение слова состояния, которое содержит сведения о классе чисел с плавающей запятой|[System::Double::IsInfinity](https://msdn.microsoft.com/en-us/library/system.double.isinfinity.aspx), [System::Double::IsNegativeInfinity](https://msdn.microsoft.com/en-us/library/system.double.isnegativeinfinity.aspx), [System::Double::IsPositiveInfinity](https://msdn.microsoft.com/en-us/library/system.double.ispositiveinfinity.aspx), [System::Double::IsNan](https://msdn.microsoft.com/en-us/library/system.double.isnan.aspx)|  
|[\_fpieee\_flt](../c-runtime-library/reference/fpieee-flt.md)|Вызов обработчика исключений и прерываний для исключений с плавающей запятой IEEE|Неприменимо.|  
|[\_fpreset](../c-runtime-library/reference/fpreset.md)|Повторная инициализация математического пакета с плавающей запятой||  
|[frexp](../c-runtime-library/reference/frexp.md)|Вычисление экспоненциального значения|Неприменимо.|  
|[\_gcvt](../c-runtime-library/reference/gcvt.md), [\_gcvt\_s](../c-runtime-library/reference/gcvt-s.md)|Преобразование числа с плавающей запятой в строку символов|[\<caps:sentence id\="tgt92" sentenceid\="ed8e24ad5c647dc4efa4fbe1e9bbc5e3" class\="tgtSentence"\>System::Convert::ToString\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.convert.tostring.aspx)|  
|[hypot, hypotf, hypotl, \_hypot, \_hypotf, \_hypotl](../c-runtime-library/reference/hypot-hypotf-hypotl-hypot-hypotf-hypotl.md)|Вычисление гипотенузы правильного треугольника|Неприменимо.|  
|[\_isnan](../c-runtime-library/reference/isnan-isnan-isnanf.md)|Проверка того, что данное значение двойной точности с плавающей запятой не является числом \(NaN\)|[\<caps:sentence id\="tgt97" sentenceid\="18f7dc07d0c506c23f2f7eb89262d274" class\="tgtSentence"\>System::Double::IsNan\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.double.isnan.aspx)|  
|[labs](../misc/labs-llabs.md)|Возвращение абсолютного значения `long`|[\<caps:sentence id\="tgt100" sentenceid\="9594ba199e25e9de6b463c8efc9fbe95" class\="tgtSentence"\>System::Math::Abs\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.math.abs.aspx)|  
|[ldexp](../c-runtime-library/reference/ldexp.md)|Вычисление произведения аргумента и 2<sup>exp</sup> \(указанная степень\)|[\<caps:sentence id\="tgt103" sentenceid\="839e85fe5fb98e8520d40a703d06932b" class\="tgtSentence"\>System::Math::Pow\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.math.pow.aspx)|  
|[ldiv](../Topic/ldiv,%20lldiv.md)|Деление одного целого числа `long` на другое, возврат частного и остатка|Неприменимо.|  
|[log, logf, log10, log10f](../Topic/log,%20logf,%20log10,%20log10f.md)|Вычисление натурального логарифма или логарифма по основанию 10|[System::Math::Log](https://msdn.microsoft.com/en-us/library/system.math.log.aspx), [System::Math::Log10](https://msdn.microsoft.com/en-us/library/system.math.log10.aspx)|  
|[\_logb](../c-runtime-library/reference/logb-logbf-logbl-logb-logbf.md)|Извлечение экспоненциального значения аргумента числа двойной точности с плавающей запятой|Неприменимо.|  
|[\_lrotl, \_lrotr](../c-runtime-library/reference/lrotl-lrotr.md)|Сдвиг `unsigned long int` влево \(`_lrotl`\) или вправо \(`_lrotr`\)|Неприменимо.|  
|[\_matherr](../c-runtime-library/reference/matherr.md)|Обработка математических ошибок|Неприменимо.|  
|[\_\_max](../c-runtime-library/reference/max.md)|Возвращение большего из двух значений|[\<caps:sentence id\="tgt121" sentenceid\="6f9dcb228534c3e5b0013615b2b1d003" class\="tgtSentence"\>System::Math::Max\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.math.max.aspx)|  
|[\_\_min](../c-runtime-library/reference/min.md)|Возвращение меньшего из двух значений|[\<caps:sentence id\="tgt124" sentenceid\="ff471983fc666dec7ba58b17a0bf76e6" class\="tgtSentence"\>System::Math::Min\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.math.min.aspx)|  
|[modf, modff](../c-runtime-library/reference/modf-modff-modfl.md)|Разбиение аргумента на целую и дробную части|Неприменимо.|  
|[nan, nanf, nanl](../c-runtime-library/reference/nan-nanf-nanl.md)|Возвращение несигнального значения NaN \(QNaN\)|[\<caps:sentence id\="tgt129" sentenceid\="c251043405ffa73fe857c83428b58fdc" class\="tgtSentence"\>System::Double::NaN\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.double.nan.aspx)|  
|[\_nextafter](../c-runtime-library/reference/nextafter-functions.md)|Возвращение следующего представимого соседнего числа|Неприменимо.|  
|[pow, powf](../Topic/pow,%20powf,%20powl.md)|Вычисление значения, возведенного в степень|[\<caps:sentence id\="tgt135" sentenceid\="839e85fe5fb98e8520d40a703d06932b" class\="tgtSentence"\>System::Math::Pow\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.math.pow.aspx)|  
|[printf, \_printf\_l, wprintf, \_wprintf\_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md), [printf\_s, \_printf\_s\_l, wprintf\_s, \_wprintf\_s\_l](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)|Запись данных в `stdout` согласно указанному формату|[System::Console::Write](https://msdn.microsoft.com/en-us/library/system.console.write.aspx), [System::Console::WriteLine](https://msdn.microsoft.com/en-us/library/system.console.writeline.aspx)|  
|[rand](../Topic/rand.md), [rand\_s](../c-runtime-library/reference/rand-s.md)|Получение псевдослучайного числа|[\<caps:sentence id\="tgt141" sentenceid\="00574fde17be9de3e07567ef5abe0110" class\="tgtSentence"\>System::Random Class\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.random.aspx)|  
|[rint, rintf, rintl](../c-runtime-library/reference/rint-rintf-rintl.md)|Округление до ближайшего целого числа в формате с плавающей запятой|[\<caps:sentence id\="tgt143" sentenceid\="1c04aeb4aeff1752cb65adabcee29f53" class\="tgtSentence"\>System::Math::Round\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.math.round.aspx)|  
|[\_rotl, \_rotr](../c-runtime-library/reference/rotl-rotl64-rotr-rotr64.md)|Сдвиг `unsigned int` влево \(`_rotl`\) или вправо \(`_rotr`\)|Неприменимо.|  
|[\_scalb](../c-runtime-library/reference/scalb.md)|Масштабирование по степеням числа 2|Неприменимо.|  
|[scalbn, scalbnf, scalbnl, scalbln, scalblnf, scalblnl](../c-runtime-library/reference/scalbn-scalbnf-scalbnl-scalbln-scalblnf-scalblnl.md)|Умножение на целую степень числа `FLT_RADIX`|Неприменимо.|  
|[scanf, wscanf](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md), [scanf\_s, \_scanf\_s\_l, wscanf\_s, \_wscanf\_s\_l](../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)|Чтение данных из `stdin` согласно указанному формату и запись данных в заданное расположение|[System::Console::Read](https://msdn.microsoft.com/en-us/library/system.console.read.aspx), [System::Console::ReadLine](https://msdn.microsoft.com/en-us/library/system.console.readline.aspx)|  
|[\_set\_controlfp](../c-runtime-library/reference/set-controlfp.md)|Задание нового значения контрольного слова|Неприменимо.|  
|[sin, sinf, sinh, sinhf](../c-runtime-library/reference/sin-sinf-sinl-sinh-sinhf-sinhl.md)|Вычисление синуса или гиперболического синуса|[System::Math::Sin](https://msdn.microsoft.com/en-us/library/system.math.sin.aspx), [System::Math::Sinh](https://msdn.microsoft.com/en-us/library/system.math.sinh.aspx)|  
|[sqrt](../c-runtime-library/reference/sqrt-sqrtf-sqrtl.md)|Нахождение квадратного корня|[\<caps:sentence id\="tgt162" sentenceid\="1a91af0bd8c63b4be64c7a0bec8dc8c4" class\="tgtSentence"\>System::Math::Sqrt\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.math.sqrt.aspx)|  
|[srand](../c-runtime-library/reference/srand.md)|Инициализация серии псевдослучайных чисел|[\<caps:sentence id\="tgt165" sentenceid\="00574fde17be9de3e07567ef5abe0110" class\="tgtSentence"\>System::Random Class\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.random.aspx)|  
|[\_status87, \_statusfp, \_statusfp2](../c-runtime-library/reference/status87-statusfp-statusfp2.md)|Получение слова состояния с плавающей запятой|Неприменимо.|  
|[strtod, \_strtod\_l, wcstod, \_wcstod\_l](../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md)|Преобразование строки символов в значение двойной точности|[\<caps:sentence id\="tgt169" sentenceid\="363f8f2cb09f8ca850491a65df66522e" class\="tgtSentence"\>System::Convert::ToDouble\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.convert.todouble.aspx)|  
|[tan, tanf, tanh, tanhf](../c-runtime-library/reference/tan-tanf-tanl-tanh-tanhf-tanhl.md)|Вычисление тангенса или гиперболического тангенса|[System::Math::Tan](https://msdn.microsoft.com/en-us/library/system.math.tan.aspx), [System::Math::Tanh](https://msdn.microsoft.com/en-us/library/system.math.tanh.aspx)|  
  
## См. также  
 [Процедуры среды выполнения по категориям](../c-runtime-library/run-time-routines-by-category.md)