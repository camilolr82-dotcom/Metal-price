import { Octokit } from "@octokit/rest";

const octokit = new Octokit({ auth: process.env.GITHUB_TOKEN });

/**
 * Crear o actualizar un archivo en GitHub
 */
export async function crearArchivo({ owner, repo, path, content }) {
  const encodedContent = Buffer.from(content).toString("base64");

  await octokit.repos.createOrUpdateFileContents({
    owner,
    repo,
    path,
    message: `Agente: creando/modificando archivo ${path}`,
    content: encodedContent,
  });

  console.log(`✅ Archivo ${path} creado/modificado en ${repo}`);
}
