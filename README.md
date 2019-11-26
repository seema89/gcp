const admin = require('firebase-admin');

admin.initializeApp({
  credential: admin.credential.applicationDefault()
});

const db = admin.firestore();

/**
 * Responds to any HTTP request.
 *
 * @param {!express:Request} req HTTP request context.
 * @param {!express:Response} res HTTP response context.
 */
exports.helloWorld = (req, res) => {
/*  let message = req.query.message || req.body.message || 'Hello World!';
  res.status(200).send(message);
  */
    return db.collection("users").add({
    first_name: "John",
    last_name: "lenon",
    created: 1000001
    });
};
