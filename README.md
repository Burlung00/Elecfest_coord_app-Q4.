# RC Low-Pass Filter Derivation

The low pass filter given is a RC low pass filter.

**System Definition**
* **$v_{in}$:** Voltage across R & C in series
* **$v_{out}$:** Voltage across C
* **$i(t) = C \frac{dv_{out}(t)}{dt}$:** current through the circuit

$$v_{in}(t) = i(t)R + v_{out}(t)$$

$$v_{in}(t) = RC \frac{dv_{out}(t)}{dt} + v_{out}(t)$$

**Using Laplace Transform**
$$V_{in}(s) = RCsV_{out}(s) + V_{out}(s)$$
$$V_{in}(s) = V_{out}(s)(1 + RCs)$$

$$H(s) = \frac{V_{out}(s)}{V_{in}(s)} = \frac{1}{1 + RCs}$$

**Substituting $s = j\omega$:**
$$H(j\omega) = \frac{1}{1 + j\omega RC}$$

# RLC Band-Pass Filter Derivation

**System Definition**
* **$v_{in}$:** Voltage across L, C, & R in series
* **$v_{out}$:** Voltage across R

$$v_{in}(t) = v_L(t) + v_C(t) + v_{out}(t)$$
$$v_{out}(t) = i(t)R \implies i(t) = \frac{v_{out}(t)}{R}$$
$$v_L(t) = L \frac{di(t)}{dt} = \frac{L}{R} \frac{dv_{out}(t)}{dt}$$
$$v_C(t) = \frac{1}{C} \int i(t) dt = \frac{1}{RC} \int v_{out}(t) dt$$

$$v_{in}(t) = \frac{L}{R} \frac{dv_{out}(t)}{dt} + \frac{1}{RC} \int v_{out}(t) dt + v_{out}(t)$$

**Using Laplace Transform**
$$V_{in}(s) = \frac{L}{R}sV_{out}(s) + \frac{1}{RCs}V_{out}(s) + V_{out}(s)$$
$$V_{in}(s) = V_{out}(s) \left( \frac{Ls}{R} + \frac{1}{RCs} + 1 \right)$$
$$V_{in}(s) = V_{out}(s) \left( \frac{LCs^2 + RCs + 1}{RCs} \right)$$

$$H(s) = \frac{V_{out}(s)}{V_{in}(s)} = \frac{RCs}{LCs^2 + RCs + 1}$$

Substituting $s = j\omega$:
$$H(j\omega) = \frac{j\omega RC}{(1 - \omega^2 LC) + j\omega RC}$$
