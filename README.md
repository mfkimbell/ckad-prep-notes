# ckad-prep-notes

## Some Quick Exam Tips

1. **Quickly Generate YAML Manifests**

   - You can use `kubectl create` along with `--dry-run=client` to generate YAML manifests quickly. For example:
     ```bash
     kubectl -n <namespace> create deploy app \
       --image=nginx:stable \
       --replicas=2 \
       --dry-run=client -o yaml > app-deploy.yaml
     ```
   - This trick can save you a lot of time instead of writing manifests from scratch.

2. **Mark Questions for Review & Move On**

   - If you get stuck, mark the question, skip it, and return later. Often, you’ll find easier questions at the end.
   - Time is limited; don’t let a single challenging task eat up all your time.

3. **Use the Official Kubectl Reference**

   - As soon as you log in, open or bookmark the official `kubectl` command reference:
     [https://kubernetes.io/docs/reference/generated/kubectl/kubectl-commands](https://kubernetes.io/docs/reference/generated/kubectl/kubectl-commands)
   - This is especially handy when you forget the exact command or flag syntax under exam pressure.

4. **Mind the Kubernetes Context**

   - Exams often use multiple contexts (clusters). Always confirm the context you’re operating on:
     ```bash
     kubectl config get-contexts
     kubectl config use-context <context-name>
     ```
   - Running commands on the wrong cluster can lead to confusing results.

5. **Back Up Files Before Modifying**

   - When editing any config or YAML, make a copy first:
     ```bash
     cp important-config.yaml important-config.yaml.bak
     ```
   - This lets you revert quickly if something goes wrong.

6. **Know Essential Docker Commands**

   - While Kubernetes is the focus, you may need Docker basics:
     - **Build** an image:  
       ```bash
       docker build -t myimage:latest .
       ```
     - **Tag** an image:  
       ```bash
       docker tag myimage:latest myregistry/myimage:v1
       ```
     - **Push** an image:  
       ```bash
       docker push myregistry/myimage:v1
       ```
     - **Save** an image as a tar file:  
       ```bash
       docker save myimage:latest -o myimage.tar
       ```
     - **Inspect** an image or container:  
       ```bash
       docker inspect myimage:latest
       ```

---

**Tip:** Practice these commands repeatedly in a test environment. Being comfortable with quick edits, context switching, and reference usage will help you manage time and stress during the exam. Good luck!
