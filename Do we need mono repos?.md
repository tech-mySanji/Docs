
https://monorepo.tools/

How it can help in our case?

We have multiple apps
1. customer 
2. vendor
3. delivery
4. branch 

There will be lots of code sharing in-between these projects and lets keep this as dry as we can. 
using a mono-repo will help to achieve this.

Does flutter support mono repos ? tooling ?

Yes, using melos.
- https://pub.dev/packages/melos
- https://melos.invertase.dev/~melos-latest/getting-started
- https://adityadroid.medium.com/flutter-at-scale-code-sharing-using-a-monorepo-a7a46c427141
- https://medium.com/flutter-community/managing-multi-package-flutter-projects-with-melos-c8ce96fa7c82

Implemented Poc: 
https://github.com/tech-mySanji/poc-mono-repo


Also supports workflow integration: 
https://github.com/marketplace/actions/melos-action

Any Issues ?
Is this an added layer and increases complexity for dev ?
Is there any other way to achieve our requirements?

Conclusion
As of now all our req can be achieved by using melos. be it common widgets/ reusable services or github actions integration. 

