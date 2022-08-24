<a name="top"></a>
<p align="center">
    <img src="_media/commander3-logo.png" height="200">
</p>

# 

# Random Text


More text here and there

Some text to see whether we have gotten the right stuff

<div class="demo-theme-preview">
  <a data-theme="vue">vue.css</a>
  <a data-theme="buble">buble.css</a>
  <a data-theme="dark">dark.css</a>
  <a data-theme="pure">pure.css</a>
</div>

<style>
  .demo-theme-preview a {
    padding-right: 10px;
  }

  .demo-theme-preview a:hover {
    cursor: pointer;
    text-decoration: underline;
  }
</style>

<script>
  var preview = Docsify.dom.find('.demo-theme-preview');
  var themes = Docsify.dom.findAll('[rel="stylesheet"]');

  preview.onclick = function (e) {
    var title = e.target.getAttribute('data-theme');

    themes.forEach(function (theme) {
      theme.disabled = theme.title !== title;
    });
  };
</script>



However, the formalism and code are designed to be flexible and extendible, and a wide range of other models may be considered after suitable code modifications.

Following Bayes Theorem, we can write the posterior distribution as
$$
P(\omega\mid \boldsymbol d) = \frac{P(\boldsymbol d\mid \omega)P(\omega)}{P(\boldsymbol d)} \propto \mathcal{L}(\omega)P(\omega),
$$
where $P(\boldsymbol d\mid \omega)\equiv\mathcal{L}(\omega)$ is called the likelihood; $P(\omega)$ is called the prior; and $P(\boldsymbol d)$ is a normalization factor.

Instead of directly explore $P(\boldsymbol d\mid \omega)\equiv\mathcal{L}(\omega)$, [Commander3](https://github.com/Cosmoglobe/Commander) heavily relies on Gibbs sampling theory which states that samples from a joint distribution may be produced by iteratively draw samples from all corresponding conditional distributions. In case of the above data model, this translates into the following Gibbs chain: 
$$
\begin{aligned}
\boldsymbol g &\leftarrow P(\boldsymbol g,\mid \boldsymbol d,\xi_n ,\Delta_\mathrm{bp} ,\boldsymbol a,\beta,C_{\ell})\\
\boldsymbol n_{\mathrm{corr}} &\leftarrow P(\boldsymbol n_{\mathrm{corr}}\mid\boldsymbol d ,\boldsymbol g ,\xi_n, \Delta_\mathrm{bp},\boldsymbol a,\beta ,C_{\ell})\\
\xi_n &\leftarrow P(\xi_n,\mid \boldsymbol d ,\boldsymbol g ,\boldsymbol n_{\mathrm{corr}} ,\Delta_\mathrm{bp} ,\boldsymbol a ,\beta ,C_{\ell})\\
\Delta_\mathrm{bp} &\leftarrow P(\Delta_\mathrm{bp},\mid \boldsymbol d ,\boldsymbol g ,\boldsymbol n_{\mathrm{corr}}, \xi_n, \boldsymbol a ,\beta ,C_{\ell})\\
\beta &\leftarrow P(\beta,\mid \boldsymbol d ,\boldsymbol g ,\boldsymbol n_{\mathrm{corr}} ,\xi_n, \Delta_\mathrm{bp} ,C_{\ell})\\
\boldsymbol a &\leftarrow P(\boldsymbol a,\mid \boldsymbol d ,\boldsymbol g ,\boldsymbol n_{\mathrm{corr}},\xi_n, \Delta_\mathrm{bp}, \beta ,C_{\ell})\\
C_{\ell} &\leftarrow P(C_{\ell},\mid \boldsymbol d ,\boldsymbol g ,\boldsymbol n_{\mathrm{corr}},\xi_n,
\Delta_\mathrm{bp}, \boldsymbol a ,\beta).
\end{aligned}
$$

# Capabilities

The latest version - `Commander3` - brings together critical features such as:

- Modern Linear Solver;
- Map Making;
- Sky and instrumental modelling;
- CMB Component Separation;
- In-memory compression of time-ordered data; 
- FFT optimization; 
- OpenMPI parallelization and load-balancing; 
- I/O efficiency;
- Fast mixing matrix computation through look-up tables.

`Commander3` is written using modern `Fortran` standards such as modules, sub modules, and object oriented derived types. The code is optimized to run on High Performance Computing (HPC) facilities, but it can also be run on your local machine.

The previous incarnation of **Commander**, - `Commander2` - is now an internal part of `Commander3`, while the first version of the code, - `Commander1` - is used mainly for debugging and/or legacy purposes.

# Installation

For installation instructions please refer to the next section.
