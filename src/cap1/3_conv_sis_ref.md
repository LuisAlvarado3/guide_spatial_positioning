# Conversión de sistema de referencia.

De acuerdo a como se señaló en el capítulo [Sistemas de Referencia](./1_sis_ref.md), algunas de las diferentes coordenadas que existen para representar un elemento (objeto) fueron definidas muy resumidamente. Sin embargo algo que se puede reconocer es que cada uno de estos sistemas es que toman una relación íntima, estas son sus componentes. En este apartado mostraré una forma de pasar de un sistema coordenado a otro con la finalidad de comprender la relación que abordan cada uno de ellos.

> Nota: Puedes tener un exceso de información con respecto de un sistema \\(\mathbb{R}^2\\) que es convertido a un sistema \\(\mathbb{R}^3\\), sin embargo es importante saber que ocurre lo contrario de un sistema de \\(\mathbb{R}^3\\) hacia un sistema \\(\mathbb{R}^2\\) en tal caso puede que los datos no sean recuperados a como eran en un principio y es mejor tratar este tipo de conversión con cautela.

## Sistemas Bidimensionales.
### Coordenadas Cartesianas-Polares.
Para una coordenada cartesiana, se verifican los valores para las dos componenetes  en el punto \\(p\\) donde sus compoenetes son \\((x,y)\\), y están dadas por por las siguientes ecuaciones:
$$
    x = r *\cos{\theta}
$$
$$
    y = r *\sin{\theta}
$$
De forma relevante se puede expresar en terminos para cualquiera de las dos ecuaciones anteriores que:
$$
    \frac{x}{r} = \cos{\theta}
$$
o bien que,
$$
    \frac{r}{x} = \sin{\theta}
$$
Para encontrar el **radio polar** \\(\vec{r}\\) es necesario convertir nuestro par de componentes \\((x,y)\\) a nuevo vector utilizando el **teorema de pitágoras**, el cual nos dice que, sea un triángulo rectángulo, la suma de dos de sus lados cada una al cuadrado es igual a la suma del tercero al cuadrado:
$$
    c^2 = a^2+b^2
$$
Dado que \\(x\\) y \\(y\\) son los lados perpendiculares, entonces, asumiremos la siguiente igualdad:
$$
    a=x\\\\
    b=y
$$
Mientras que el lado **adyacente** es equivalente al escalar \\(r\\) del vector como,
$$
    ||\vec{r}|| = c = r
$$
si,
$$
    c^2 = a^2+b^2 \\\\
    \Rightarrow \sqrt{c^2} = \sqrt{a^2+b^2}\\\\
    \Rightarrow c = \sqrt{a^2+b^2}
$$

Igualamos entonces los términos con las componentes del punto \\(p\\), y obtenemos la siguiente igualdad,

$$
    ||\vec{r}||= \sqrt{x^2+y^2}
$$
Para obtener el **ángulo polar** despejamos cualquiera de las primeras ecuaciones,
$$
    \frac{x}{r} = \cos{\theta}\\\\
    \Rightarrow \theta = \cos^{-1}{(\frac{x}{r})} = \cos{(\frac{r}{x})}\\\\
    \Rightarrow \theta = \cos{(\frac{ \sqrt{x^2+y^2} }{x})}
$$ 
Por lo tanto la expresión de conversión para obtener las **coordenadas polares** con respecto a **coordenadas cartesianas** es,
$$
    \vec{r} = \cases{
        r = \sqrt{x^2+y^2}\\\\
        \theta = \cos{(\frac{ \sqrt{x^2+y^2} }{x})}
    }
$$
Mientras que para pasar de un sistema de **coordenadas polares** a **coordenadas rectangulares** se refleja como,
$$
    p = \cases{
        x = r *\cos{\theta}\\\\
        y = r *\sin{\theta}
    }
$$

## Sistemas Tridimensiones.
### Coordenadas Cartesianas-Cilíndricas.
Supongase una **coordenada cartesiana** dada por el punto \\(p\\) en el espacio por las componentes \\((x,y,z)\\) y el vector \\(\vec{r}\\) sean sus componentes \\((r, \theta, z)\\) dado por las **coordenadas cilíndricas**, donde el componente perpendicular común sea \\(z\\), la expresión de conversión de **coordenadas cilíndricas** respecto de los ejes en las **coordenadas cartesianas** es,
$$
  \vec{r} = \cases{
        r = \sqrt{x^2+y^2}\\\\
        \theta = \cos{(\frac{ \sqrt{x^2+y^2} }{x})}\\\\
        z = z
    }  
$$
Y viseversa, de **coordenadas cilíndricas** a **rectangulares** es,
$$
    p = \cases{
        x = r *\cos{\theta}\\\\
        y = r *\sin{\theta}\\\\
        z = z
    }
$$
### Coordenadas Cartesianas-Esféricas.
Sea el punto **cartesiano** \\(p_{cartesiana}\\) por sus componentes \\((x,y,z)\\) y un punto \\(p_{esférica}\\) **esférico** regido por sus componentes \\( (\rho, \phi, \theta) \\), tal que \\(\rho\\) es el factor adyacente en los tres ejes \\((x,y,z)\\), seguido por las siguientes expresiones, 
$$
    x = \rho \sin{\phi} \cos{\theta}\\\\
    y = \rho \sin{\phi} \sin{\theta}\\\\
    z = \rho \cos{\phi}
$$
La primer ecuación de acuerdo con el teorema de pitagoras para un modelo \\(\mathbb{R}^3\\) consta de,
$$
    \rho = \sqrt{ x^2 + y^2 + z^2}
$$

Para obtener a \\(\phi\\) simplemente despejando a \\(z\\),
$$
    \cos{\phi} = \frac{z}{\rho} = \frac{z}{\sqrt{ x^2 + y^2 + z^2}}\\\\
    \Rightarrow \phi = \cos^{-1}{ (\frac{z}{\sqrt{ x^2 + y^2 + z^2}}) } = \cos{ (\frac{\sqrt{ x^2 + y^2 + z^2}}{z}) }\\\\
    \therefore \phi = \cos{ (\frac{\sqrt{ x^2 + y^2 + z^2}}{z}) }
$$
Para la componenete \\(\theta\\) de igual manera podemos despejar cualquiera de las primeras ecuaciones,
$$
    x = \rho \sin{\phi} \cos{\theta}\\\\
    \Rightarrow \frac{x}{\rho \sin{\phi}} =  \cos{\theta}\\\\
    \Rightarrow \theta = \cos^{-1}{( \frac{x}{\rho \sin{\phi}} )} = \cos{( \frac{\rho \sin{\phi}}{x} )}\\\\
    \theta = \cos{( \frac{\rho \sin{ (\cos{ (\frac{\sqrt{ x^2 + y^2 + z^2}}{z}) }) }}{x} )} = \cos{( \frac{\sqrt{ x^2 + y^2 + z^2} * \sin{ (\cos{ (\frac{\sqrt{ x^2 + y^2 + z^2}}{z}) }) }}{x} )}\\\\
    \therefore \theta = \cos{( \frac{\sqrt{ x^2 + y^2 + z^2} * \sin{ (\cos{ (\frac{\sqrt{ x^2 + y^2 + z^2}}{z}) }) }}{x} )}
$$
Entonces, la forma de expresar **coordenadas esféricas** mediante su forma **rectangular** es,
$$
    p_{esférica} = \cases{
        \rho = \sqrt{ x^2 + y^2 + z^2}\\\\
        \phi = \cos{ (\frac{\sqrt{ x^2 + y^2 + z^2}}{z}) }\\\\
        \theta = \cos{( \frac{\sqrt{ x^2 + y^2 + z^2} * \sin{ (\cos{ (\frac{\sqrt{ x^2 + y^2 + z^2}}{z}) }) }}{x} )}
    }
$$
Mientras que, para expresar **coordenadas cartesianas** mediante su forma **esférica** se define como,
$$
    p_{cartesiana} = \cases{
        x = \rho \sin{\phi} \cos{\theta}\\\\
        y = \rho \sin{\phi} \sin{\theta}\\\\
        z = \rho \cos{\phi}
    }
$$

### Coordenadas Cilíndricas-Esféricas.


## Sistemas Mixtos.
### Sistemas de \\(\mathbb{R}^2\\) a \\(\mathbb{R}^3\\).

### Sistemas de \\(\mathbb{R}^3\\) a \\(\mathbb{R}^2\\) sin sufrir pérdidas de información.
