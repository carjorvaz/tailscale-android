# Tailscale Android Client

Personal fork of Tailscale's Android client.
Needed because I wasn't able to select an external server on GrapheneOS.
When I tapped the button "Save and restart", the app crashed and kept redirecting me to tailscale's login page.
[Likely a GrapheneOS-specific issue.](https://forum.tailscale.com/t/tailscale-with-headscale-with-graphene-os/3312)

[Relevant commit where I set my external server as the default server.](https://github.com/carjorvaz/tailscale-android/commit/1846cc4da3896cf914c752372166948ede4a3d7e)

## Installation steps:
-  [Sync fork](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/syncing-a-fork)

- Clone repo:
``` sh
git clone git@github.com:carjorvaz/tailscale-android.git 
```

- Create and enter container:
``` sh
make dockershell
```

- Create apk inside container:
``` sh
make tailscale-debug.apk
```

- Copy apk from container to host system:
``` sh
docker ps
docker cp <container_id>:/build/tailscale-android/tailscale-debug.apk ~
```

- Copy and install on android device.

## Reference
- https://github.com/juanfont/headscale/issues/146#issuecomment-953690497
