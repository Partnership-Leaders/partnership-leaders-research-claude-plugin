# Onboarding Email Copy

Use this copy in Supabase Authentication -> Emails -> Confirm sign up.

```html
<h2>Confirm your Partnership Leaders Research account</h2>

<p>Click below to verify your email and finish setting up your account.</p>

<p><a href="{{ .ConfirmationURL }}">Confirm email</a></p>

<p>After confirming your email, connect Partnership Leaders Research to Claude here:</p>

<p>
  <a href="https://claude.ai/customize/connectors?modal=add-custom-connector&connectorName=Partnership%20Leaders%20Research&connectorUrl=https%3A%2F%2Fsi-research-dashboard-production-25d8.up.railway.app%2Fmcp">
    Add Partnership Leaders Research to Claude
  </a>
</p>

<p>If you see "authorization not found" after confirming your email, reopen the Claude connector link above and click Connect again. That message means the first Claude authorization window expired, not that your account failed.</p>

<p>Sample questions to try:</p>

<ul>
  <li>How are AI partner programs becoming harder or more selective for partners?</li>
  <li>Which companies are changing partner incentives or marketplace routes in ways a VP of Partnerships should act on?</li>
  <li>What should a Head of Ecosystems watch from recent AI partnership moves?</li>
</ul>
```

