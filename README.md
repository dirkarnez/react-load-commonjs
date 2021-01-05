react-load-commonjs
===================
```
import { useEffect } from 'react';

const useScript = url => {
  useEffect(() => {
    const script = document.createElement('script');

    script.src = url;
    script.async = true;

    document.body.appendChild(script);

    return () => {
      document.body.removeChild(script);
    }
  }, [url]);
};

export default useScript;
Which can be used like so:

import useScript from 'hooks/useScript';

const MyComponent = props => {
  useScript('https://use.typekit.net/foobar.js');

  // rest of your component
}
```
